# @compilr-dev/agents

```
      \|/
    ╭══════════╮     ___  ___  _ __ ___  _ __ (_) |_ __
    ║'  ▐▌  ▐▌ │    / __|/ _ \| '_ ` _ \| '_ \| | | '__|
    ║          │   | (__| (_) | | | | | | |_) | | | |
    ╰─═──────═─╯    \___|\___/|_| |_| |_| .__/|_|_|_|
      \________\                        | | .dev
                                        |_| agents
```

> Lightweight multi-LLM agent library for building CLI AI assistants

[![npm version](https://img.shields.io/npm/v/@compilr-dev/agents.svg)](https://www.npmjs.com/package/@compilr-dev/agents)
[![License: FSL-1.1-MIT](https://img.shields.io/badge/License-FSL--1.1--MIT-blue.svg)](https://fsl.software/)
[![API Docs](https://img.shields.io/badge/API_Docs-GitHub_Pages-blue)](https://compilr-dev.github.io/agents/)

**[API Reference](https://compilr-dev.github.io/agents/)** | **[llms.txt](https://compilr.dev/llms.txt)** (for AI agents)

> [!WARNING]
> This package is in beta. APIs may change between minor versions.

## Features

- **Multi-LLM Support**: 9 providers -- Claude, OpenAI, Gemini, Ollama (local), Together AI, Groq, Fireworks, Perplexity, OpenRouter
- **17 Built-in Tools**: File ops, bash, grep, glob, edit, web fetch, sub-agents, todos, backlog, and more
- **Sub-agents**: Spawn specialized agents for complex tasks (9 built-in agent types)
- **11 Skills**: Reusable prompt templates for common workflows
- **Context Management**: Token budgeting, compaction, summarization
- **Event Streaming**: Real-time execution monitoring with typed events and abort support
- **Anchors**: Critical information that survives context compaction
- **Guardrails**: 15 built-in patterns for safety checks (warn/confirm/block)
- **Permissions**: Tool-level access control (always/session/once/deny) with wildcards
- **Project Memory**: Auto-loads CLAUDE.md, GEMINI.md, CURSOR.md, and more
- **Hooks System**: Lifecycle hooks for beforeChat, afterChat, beforeToolCall, afterToolCall
- **Rate Limiting**: Automatic retry with exponential backoff
- **TypeScript First**: Full type safety with strict mode

## Installation

```bash
npm install @compilr-dev/agents
```

For Claude support:
```bash
npm install @compilr-dev/agents @anthropic-ai/sdk
```

## Quick Start

```typescript
import { Agent, MockProvider } from '@compilr-dev/agents';

// Create an agent with a provider
const provider = new MockProvider();
provider.addResponse('Hello! How can I help you today?');

const agent = new Agent({
  provider,
  systemPrompt: 'You are a helpful assistant.',
});

// Run the agent
const result = await agent.run('Hello!');
console.log(result.response);  // "Hello! How can I help you today?"
console.log(result.iterations); // 1
```

### With Claude

```typescript
import { Agent, ClaudeProvider } from '@compilr-dev/agents';

const agent = new Agent({
  provider: new ClaudeProvider({ apiKey: process.env.ANTHROPIC_API_KEY }),
  systemPrompt: 'You are a helpful coding assistant.',
  maxIterations: 10,
});

const result = await agent.run('Explain async/await in JavaScript');
console.log(result.response);
```

## Core Concepts

### Agent

The `Agent` class orchestrates LLM interactions and tool execution:

```typescript
import { Agent, ClaudeProvider } from '@compilr-dev/agents';

const agent = new Agent({
  provider: new ClaudeProvider({ apiKey: 'your-key' }),
  systemPrompt: 'You are a helpful assistant.',
  maxIterations: 10,  // Default: 10
  onEvent: (event) => {
    // Real-time execution monitoring
    console.log(event.type);
  },
});
```

### Messages

The library provides utilities for working with conversation messages:

```typescript
import {
  createUserMessage,
  createAssistantMessage,
  createToolResultMessage,
  getTextContent
} from '@compilr-dev/agents';

// Create messages
const userMsg = createUserMessage('Hello!');
const assistantMsg = createAssistantMessage('Hi there!');

// Extract text from message with multiple content blocks
const text = getTextContent(assistantMsg);
```

### Tools

Define tools that agents can use:

```typescript
import { defineTool, createSuccessResult, createErrorResult } from '@compilr-dev/agents';

const calculatorTool = defineTool({
  name: 'calculator',
  description: 'Perform basic math operations',
  inputSchema: {
    type: 'object',
    properties: {
      operation: { type: 'string', description: 'add, subtract, multiply, divide' },
      a: { type: 'number' },
      b: { type: 'number' },
    },
    required: ['operation', 'a', 'b'],
  },
  execute: async ({ operation, a, b }) => {
    switch (operation) {
      case 'add': return createSuccessResult(a + b);
      case 'subtract': return createSuccessResult(a - b);
      case 'multiply': return createSuccessResult(a * b);
      case 'divide':
        if (b === 0) return createErrorResult('Division by zero');
        return createSuccessResult(a / b);
      default:
        return createErrorResult(`Unknown operation: ${operation}`);
    }
  },
});

// Register with agent
agent.registerTool(calculatorTool);
```

### Tool Registry

Manage tools with the registry:

```typescript
import { DefaultToolRegistry, defineTool } from '@compilr-dev/agents';

const registry = new DefaultToolRegistry();

// Register tools
registry.register(myTool);

// Get tool definitions for LLM
const definitions = registry.getDefinitions();

// Execute a tool
const result = await registry.execute('tool_name', { arg: 'value' });
```

## Built-in Tools

### File Operations

```typescript
import { readFileTool, writeFileTool } from '@compilr-dev/agents';

agent.registerTool(readFileTool);
agent.registerTool(writeFileTool);
```

### Bash Execution

```typescript
import { createBashTool } from '@compilr-dev/agents';

const bashTool = createBashTool({
  workingDir: '/path/to/project',
  timeout: 30000,  // 30 seconds
  allowedCommands: ['git', 'npm', 'ls'],  // Optional whitelist
});

agent.registerTool(bashTool);
```

## Event System

Monitor agent execution in real-time:

```typescript
import type { AgentEvent } from '@compilr-dev/agents';

const agent = new Agent({
  provider,
  onEvent: (event: AgentEvent) => {
    switch (event.type) {
      case 'iteration_start':
        console.log(`Starting iteration ${event.iteration}`);
        break;
      case 'llm_start':
        console.log('LLM thinking...');
        break;
      case 'llm_end':
        console.log(`LLM done, tool uses: ${event.hasToolUses}`);
        break;
      case 'tool_start':
        console.log(`Calling tool: ${event.name}`);
        break;
      case 'tool_end':
        console.log(`Tool result: ${event.result.success}`);
        break;
      case 'done':
        console.log(`Final: ${event.response}`);
        break;
    }
  },
});
```

### Streaming Events

For CLI applications, stream events as they happen:

```typescript
for await (const event of agent.stream('Hello!')) {
  if (event.type === 'llm_chunk') {
    process.stdout.write(event.chunk.text || '');
  }
}
```

## Abort Support

Cancel running agents:

```typescript
const controller = new AbortController();

// Cancel after 5 seconds
setTimeout(() => controller.abort(), 5000);

try {
  const result = await agent.run('Complex task...', {
    signal: controller.signal,
  });
} catch (error) {
  if (error instanceof AbortError) {
    console.log('Agent was cancelled');
  }
}
```

## Error Handling

The library provides specific error types:

```typescript
import {
  AgentError,
  ProviderError,
  ToolError,
  ValidationError,
  MaxIterationsError,
  AbortError,
  isAgentError,
  isProviderError,
  isToolError,
  wrapError,
} from '@compilr-dev/agents';

try {
  await agent.run('...');
} catch (error) {
  if (isProviderError(error)) {
    console.log(`Provider ${error.provider} failed: ${error.message}`);
  } else if (isToolError(error)) {
    console.log(`Tool ${error.toolName} failed: ${error.message}`);
  } else if (error instanceof MaxIterationsError) {
    console.log(`Reached max iterations: ${error.maxIterations}`);
  }
}
```

## Providers

### Built-in Providers

```typescript
import {
  ClaudeProvider,     // Anthropic Claude
  OpenAIProvider,     // OpenAI GPT
  GeminiProvider,     // Google Gemini
  OllamaProvider,     // Local models (no API key)
  TogetherProvider,   // Together AI
  GroqProvider,       // Groq (fast inference)
  FireworksProvider,  // Fireworks AI
  PerplexityProvider, // Perplexity (search-augmented)
  OpenRouterProvider, // OpenRouter (multi-provider)
} from '@compilr-dev/agents';

// Claude (recommended)
const claude = new ClaudeProvider({
  apiKey: process.env.ANTHROPIC_API_KEY,
  model: 'claude-sonnet-4-20250514',
});

// OpenAI
const openai = new OpenAIProvider({
  apiKey: process.env.OPENAI_API_KEY,
  model: 'gpt-4o',
});

// Gemini
const gemini = new GeminiProvider({
  apiKey: process.env.GOOGLE_API_KEY,
  model: 'gemini-2.0-flash',
});

// Ollama (local, no API key)
const ollama = new OllamaProvider({
  model: 'llama3.1:8b',
  baseUrl: 'http://localhost:11434',
});
```

### MockProvider (for testing)

```typescript
import { MockProvider } from '@compilr-dev/agents';

const provider = new MockProvider();

// Queue responses
provider.addResponse('Simple text response');
provider.addResponse({
  text: 'Using a tool...',
  toolCalls: [{ id: 'call_1', name: 'my_tool', input: { arg: 'value' } }],
});

// Queue an error
provider.addError(new Error('API failed'));

// Add delay
provider.addResponse('Delayed response', 1000);

// Access history
console.log(provider.history);  // All chat() calls
```

### Custom Providers

Implement the `LLMProvider` interface:

```typescript
import type { LLMProvider, Message, ChatOptions, StreamChunk } from '@compilr-dev/agents';

class MyProvider implements LLMProvider {
  readonly name = 'my-provider';

  async *chat(
    messages: Message[],
    options?: ChatOptions
  ): AsyncIterable<StreamChunk> {
    // Your implementation
    yield { type: 'text', text: 'Response text' };
    yield { type: 'end', stopReason: 'end_turn' };
  }

  async countTokens(messages: Message[]): Promise<number> {
    // Optional token counting
    return messages.length * 100;
  }
}
```

## API Reference

### Agent

```typescript
class Agent {
  constructor(options: AgentOptions);

  // Run agent and return final result
  run(userMessage: string, options?: RunOptions): Promise<AgentResult>;

  // Stream events during execution
  stream(userMessage: string, options?: RunOptions): AsyncIterable<AgentEvent>;

  // Tool management
  registerTool(tool: Tool): void;
  registerTools(tools: Tool[]): void;
  getToolDefinitions(): ToolDefinition[];
}
```

### Types

```typescript
interface AgentOptions {
  provider: LLMProvider;
  systemPrompt?: string;
  maxIterations?: number;
  onEvent?: (event: AgentEvent) => void;
}

interface RunOptions {
  signal?: AbortSignal;
}

interface AgentResult {
  response: string;
  iterations: number;
  toolCalls: ToolCallInfo[];
}

type AgentEvent =
  | { type: 'iteration_start'; iteration: number }
  | { type: 'llm_start' }
  | { type: 'llm_chunk'; chunk: StreamChunk }
  | { type: 'llm_end'; text: string; hasToolUses: boolean }
  | { type: 'tool_start'; name: string; input: Record<string, unknown> }
  | { type: 'tool_end'; name: string; result: ToolExecutionResult }
  | { type: 'iteration_end'; iteration: number }
  | { type: 'done'; response: string };
```

## Context Management

Manage context windows in long-running agent sessions:

```typescript
import { ContextManager, DEFAULT_CONTEXT_CONFIG } from '@compilr-dev/agents';

const contextManager = new ContextManager({
  provider,
  config: {
    maxContextTokens: 200000,  // Claude's limit
    compaction: {
      triggerThreshold: 0.5,   // Compact at 50% utilization
      preserveRecentTurns: 10, // Keep last 10 turns
    },
    summarization: {
      triggerThreshold: 0.9,   // Summarize at 90%
      preserveRecentMessages: 6,
    },
  },
  onEvent: (event) => {
    if (event.type === 'context_warning') {
      console.log(`Context at ${event.utilization * 100}%`);
    }
  },
});

// Track token usage
await contextManager.updateTokenCount(messages);
console.log(`Utilization: ${contextManager.getUtilization() * 100}%`);

// Check if action needed
if (contextManager.needsSummarization()) {
  const { messages: summarized } = await contextManager.summarize(
    messages,
    async (msgs) => 'Summary of conversation...'  // Your LLM call
  );
}

// Filter large content before adding
const { content, filtered } = contextManager.filterContent(
  largeToolResult,
  'tool_result'
);
```

### Context Strategies

| Strategy | Trigger | Reversible | Description |
|----------|---------|------------|-------------|
| **Filtering** | Before add | N/A | Truncate large content (>80K tokens) |
| **Compaction** | 50% or 20 turns | Yes | Save old results to files |
| **Summarization** | 90% | No | Compress entire history |

## Anchors (Critical Information Persistence)

Anchors are critical pieces of information that survive context compaction. They're automatically re-injected into every LLM call:

```typescript
import { Agent, AnchorManager, ClaudeProvider } from '@compilr-dev/agents';

const agent = new Agent({
  provider: new ClaudeProvider({ apiKey: process.env.ANTHROPIC_API_KEY }),
  systemPrompt: 'You are a helpful assistant.',
  anchors: {
    maxAnchors: 20,        // Maximum number of anchors
    maxTokens: 2000,       // Token budget for anchors
    includeDefaults: true, // Include safety anchors (git, file operations)
  },
});

// Add a session anchor (survives until session ends)
agent.addAnchor({
  content: 'User prefers TypeScript with strict mode',
  priority: 'critical',
  scope: 'session',
});

// Add a persistent anchor (saved to disk)
agent.addAnchor({
  content: 'Never modify files in /etc',
  priority: 'safety',
  scope: 'persistent',
  tags: ['filesystem'],
});

// Add a temporary anchor (expires after a time)
agent.addAnchor({
  content: 'Currently debugging the auth module',
  priority: 'info',
  scope: 'temporary',
  expiresAt: new Date(Date.now() + 3600000), // 1 hour
});
```

### Anchor Priorities

| Priority | Description | Format in LLM |
|----------|-------------|---------------|
| `critical` | Must remember | `### CRITICAL (Must Remember)` |
| `safety` | Check before acting | `### SAFETY (Check Before Acting)` |
| `info` | Contextual information | `### INFO` |

### Standalone AnchorManager

```typescript
import { AnchorManager } from '@compilr-dev/agents';

const anchors = new AnchorManager({
  maxAnchors: 20,
  maxTokens: 2000,
  persistPath: '~/.myapp/anchors.json',  // Optional persistence
  includeDefaults: true,
});

// Add anchors
anchors.add({ content: 'Important info', priority: 'critical', scope: 'session' });

// Query anchors
const critical = anchors.getAll({ priority: 'critical' });
const tagged = anchors.getAll({ tags: ['git'] });

// Format for LLM injection
const formatted = anchors.format();
// Returns:
// ### CRITICAL (Must Remember)
// - Important info

// Monitor token usage
console.log(`Utilization: ${anchors.getUtilization() * 100}%`);
```

## Guardrails (Safety Checks)

Guardrails are pattern-based safety checks that run before tool execution. They can warn, require confirmation, or block dangerous operations:

```typescript
import { Agent, ClaudeProvider } from '@compilr-dev/agents';

const agent = new Agent({
  provider: new ClaudeProvider({ apiKey: process.env.ANTHROPIC_API_KEY }),
  systemPrompt: 'You are a helpful assistant.',
  guardrails: {
    enabled: true,
    includeDefaults: true, // 15 built-in patterns for git, rm, DROP TABLE, etc.
    custom: [
      {
        id: 'no-prod-db',
        name: 'Production Database Protection',
        description: 'Prevent operations on production database',
        patterns: [/prod.*db/i, /production.*database/i],
        action: 'block',  // 'warn' | 'confirm' | 'block'
        message: 'Operations on production database are blocked',
        scope: ['bash'],  // Optional: limit to specific tools
        tags: ['database', 'production'],
      },
    ],
    onTriggered: async (result, context) => {
      // Handle 'confirm' actions
      if (result.action === 'confirm') {
        return await askUserConfirmation(result.guardrail.message);
      }
      return result.action !== 'block';
    },
  },
});
```

### Built-in Guardrails

| ID | Action | Pattern | Description |
|----|--------|---------|-------------|
| `git-reset-hard` | confirm | `git reset --hard` | Prevents accidental loss of uncommitted changes |
| `git-push-force` | confirm | `git push --force` | Prevents force pushing to branches |
| `rm-rf` | confirm | `rm -rf` | Prevents recursive deletion |
| `rm-root` | block | `rm -rf /` | Blocks deletion of root filesystem |
| `drop-table` | confirm | `DROP TABLE` | Prevents accidental table deletion |
| `truncate-table` | confirm | `TRUNCATE` | Prevents data loss |
| `delete-where-all` | warn | `DELETE FROM` without WHERE | Warns about deleting all rows |
| `secrets-env` | warn | API keys, passwords | Warns about exposing secrets |
| `chmod-777` | warn | `chmod 777` | Warns about insecure permissions |
| `curl-pipe-bash` | block | `curl | bash` | Blocks unsafe remote execution |
| `eval-code` | warn | `eval()` patterns | Warns about code injection risks |
| `sudo-rm` | confirm | `sudo rm` | Confirms privileged deletion |
| `git-clean` | confirm | `git clean -fd` | Confirms removing untracked files |
| `format-disk` | block | `mkfs`, `dd` | Blocks disk formatting |
| `kill-all` | confirm | `killall`, `pkill` | Confirms killing processes |

### Standalone GuardrailManager

```typescript
import { GuardrailManager, getGuardrailsByTag } from '@compilr-dev/agents';

const guardrails = new GuardrailManager({
  enabled: true,
  includeDefaults: true,
});

// Check before tool execution
const result = guardrails.check('bash', { command: 'rm -rf /tmp/test' });
if (result.triggered) {
  console.log(`Guardrail triggered: ${result.guardrail.name}`);
  console.log(`Action: ${result.action}`);  // 'warn' | 'confirm' | 'block'
  console.log(`Message: ${result.guardrail.message}`);
}

// Check and handle (with confirmation callback)
const { proceed, result } = await guardrails.checkAndHandle('bash', input);
if (!proceed) {
  console.log('Operation blocked by guardrail');
}

// Get guardrails by tag
const gitGuardrails = getGuardrailsByTag('git');
const destructiveGuardrails = getGuardrailsByTag('destructive');

// Enable/disable individual guardrails
guardrails.disable('rm-rf');
guardrails.enable('rm-rf');
```

### Guardrail Events

Monitor guardrail activity:

```typescript
guardrails.onEvent((event) => {
  switch (event.type) {
    case 'guardrail:triggered':
      console.log(`Guardrail ${event.result.guardrail.name} triggered`);
      break;
    case 'guardrail:blocked':
      console.log('Operation blocked');
      break;
    case 'guardrail:warning':
      console.log('Warning issued');
      break;
    case 'guardrail:confirmed':
      console.log('User confirmed dangerous operation');
      break;
    case 'guardrail:cancelled':
      console.log('User cancelled operation');
      break;
  }
});
```

## Permissions (Tool-level Access Control)

Permissions provide fine-grained control over which tools can execute and when user approval is required:

```typescript
import { Agent, ClaudeProvider } from '@compilr-dev/agents';

const agent = new Agent({
  provider: new ClaudeProvider({ apiKey: process.env.ANTHROPIC_API_KEY }),
  systemPrompt: 'You are a helpful assistant.',
  permissions: {
    enabled: true,
    defaultLevel: 'always',  // Default for tools without rules
    includeDefaults: true,   // Include default rules for bash, write_file, edit
    rules: [
      { toolName: 'bash', level: 'once', description: 'Shell commands' },
      { toolName: 'write_file', level: 'session', description: 'File writes' },
      { toolName: 'delete_*', level: 'deny', description: 'Delete operations' },
    ],
    onPermissionRequest: async (request) => {
      // Handle permission requests (e.g., prompt user)
      console.log(`Tool: ${request.toolName}`);
      console.log(`Preview: ${request.preview}`);
      return await askUser(`Allow ${request.toolName}?`);
    },
  },
});
```

### Permission Levels

| Level | Description | Behavior |
|-------|-------------|----------|
| `always` | No approval needed | Tool executes immediately |
| `session` | Ask once per session | After approval, tool runs freely |
| `once` | Ask every time | User must approve each execution |
| `deny` | Always blocked | Tool cannot execute |

### Wildcard Patterns

Permission rules support wildcards for flexible matching:

```typescript
// Match all tools starting with "delete_"
{ toolName: 'delete_*', level: 'deny' }

// Match all tools ending with "_file"
{ toolName: '*_file', level: 'session' }

// Match tools containing "dangerous"
{ toolName: '*dangerous*', level: 'once' }
```

### Standalone PermissionManager

```typescript
import { PermissionManager } from '@compilr-dev/agents';

const permissions = new PermissionManager({
  enabled: true,
  defaultLevel: 'always',
  onPermissionRequest: async (request) => {
    return await promptUser(request.preview);
  },
});

// Add rules dynamically
permissions.addRule({
  toolName: 'bash',
  level: 'once',
  description: 'Shell commands',
  tags: ['shell', 'dangerous'],
});

// Check permission before execution
const result = await permissions.check('bash', { command: 'rm -rf /tmp/test' });
if (result.allowed) {
  // Proceed with execution
} else {
  console.log(`Denied: ${result.reason}`);
}

// Grant session-level permission programmatically
permissions.grantSession('write_file');

// Check if tool has session grant
if (permissions.hasSessionGrant('write_file')) {
  console.log('write_file approved for this session');
}
```

### Permission Events

Monitor permission activity:

```typescript
permissions.onEvent((event) => {
  switch (event.type) {
    case 'permission:granted':
      console.log(`${event.toolName} allowed`);
      break;
    case 'permission:denied':
      console.log(`${event.toolName} denied`);
      break;
    case 'permission:asked':
      console.log(`Asking about ${event.toolName}`);
      break;
    case 'permission:session_granted':
      console.log(`${event.toolName} approved for session`);
      break;
  }
});
```

### Permissions vs Guardrails

Both systems provide safety, but serve different purposes:

| Aspect | Permissions | Guardrails |
|--------|-------------|------------|
| **Purpose** | Access control | Content safety |
| **Scope** | Tool-level | Input patterns |
| **Timing** | Before tool call | Before execution |
| **Typical Use** | "Can this tool run?" | "Is this input safe?" |
| **User Interaction** | Session/once approval | Confirm dangerous ops |

Use them together for comprehensive safety:
- Permissions control *which* tools can be used
- Guardrails check *what* inputs are safe

## Project Memory (CLAUDE.md, GEMINI.md, etc.)

Project Memory automatically discovers and loads project-specific instructions from markdown files. It supports various LLM-specific naming conventions:

| Provider | Files Searched |
|----------|----------------|
| Claude | `CLAUDE.md`, `.claude.md`, `.claude/instructions.md` |
| Gemini | `GEMINI.md`, `.gemini.md`, `.gemini/instructions.md` |
| OpenAI/GPT | `OPENAI.md`, `GPT.md`, `CHATGPT.md` |
| Copilot | `COPILOT.md`, `.github/copilot-instructions.md` |
| Cursor | `CURSOR.md`, `.cursorrules`, `.cursor/rules` |
| Generic | `PROJECT.md`, `INSTRUCTIONS.md`, `AI.md`, `CONTEXT.md` |

### Using with Agent

```typescript
import { Agent, ClaudeProvider } from '@compilr-dev/agents';

// Option 1: Factory method (recommended)
const agent = await Agent.createWithMemory(
  {
    provider: new ClaudeProvider({ apiKey: process.env.ANTHROPIC_API_KEY }),
    systemPrompt: 'You are a helpful assistant.',
  },
  { providers: 'claude', includeGeneric: true },
  '/path/to/project'  // defaults to cwd
);

// Access loaded memory
const memory = agent.getProjectMemory();
console.log(`Loaded ${memory?.files.length} instruction files`);

// Option 2: Pre-load memory manually
import { ProjectMemoryLoader } from '@compilr-dev/agents';

const loader = new ProjectMemoryLoader({
  providers: ['claude', 'gemini'],
  includeGeneric: true,
});
const memory = await loader.load('/path/to/project');

const agent = new Agent({
  provider,
  systemPrompt: 'You are a helpful assistant.',
  projectMemory: memory,
});
```

### Multiple Providers

Search for instructions from multiple LLM providers:

```typescript
const agent = await Agent.createWithMemory(
  { provider },
  {
    providers: ['claude', 'gemini', 'openai'],
    includeGeneric: true,  // Also search PROJECT.md, AI.md, etc.
    combineStrategy: 'concat',  // Combine all found files
  }
);
```

### ProjectMemoryLoader Options

```typescript
const loader = new ProjectMemoryLoader({
  // Provider(s) to search for
  providers: 'claude',  // or ['claude', 'gemini']

  // Include generic patterns (PROJECT.md, AI.md, etc.)
  includeGeneric: true,

  // Search parent directories up to git root
  searchParents: true,
  stopAtGitRoot: true,
  maxParentDepth: 10,

  // How to combine multiple files
  combineStrategy: 'concat',  // 'concat' | 'priority' | 'dedupe'

  // Content limits
  maxContentSize: 100000,  // 100KB max

  // Headers in combined output
  includeHeaders: true,
  headerFormat: '# From: {relativePath}\n\n',
});
```

### Combine Strategies

| Strategy | Description |
|----------|-------------|
| `concat` | Concatenate all files with separators (default) |
| `priority` | Use only the highest priority file |
| `dedupe` | Concatenate but remove duplicate content |

### Custom Patterns

Add custom file patterns for your own naming conventions:

```typescript
const loader = new ProjectMemoryLoader({
  providers: 'claude',
  customPatterns: [
    { pattern: 'TEAM-RULES.md', priority: 0, description: 'Team rules' },
    { pattern: '.ai-config.md', priority: 1, description: 'AI config' },
  ],
});
```

### Standalone Usage

Use the loader without an Agent:

```typescript
import {
  loadProjectMemory,
  hasProjectMemory,
  getSupportedProviders,
  getProviderPatterns,
} from '@compilr-dev/agents';

// Quick check if memory files exist
if (await hasProjectMemory('/path/to/project', { providers: 'claude' })) {
  console.log('Found project instructions!');
}

// Load memory directly
const memory = await loadProjectMemory('/path/to/project', {
  providers: ['claude', 'gemini'],
});

console.log(`Loaded ${memory.files.length} files`);
console.log(`Estimated tokens: ${memory.estimatedTokens}`);

// Get patterns for a provider
const patterns = getProviderPatterns('cursor');
// Returns: [{ pattern: 'CURSOR.md', ... }, { pattern: '.cursorrules', ... }]

// List all supported providers
const providers = getSupportedProviders();
// Returns: ['claude', 'anthropic', 'gemini', 'openai', 'gpt', 'copilot', 'cursor', 'codeium']
```

## Rate Limiting

Protect against API rate limits with automatic retry and backoff:

```typescript
import { Agent, ClaudeProvider, createRateLimitedProvider } from '@compilr-dev/agents';

// Wrap any provider with rate limiting
const provider = createRateLimitedProvider(
  new ClaudeProvider({ apiKey: process.env.ANTHROPIC_API_KEY }),
  {
    maxRequestsPerMinute: 50,
    maxTokensPerMinute: 100000,
    maxRetries: 3,
    initialBackoffMs: 1000,
    maxBackoffMs: 60000,
    backoffMultiplier: 2,
    onRateLimited: (info) => {
      console.log(`Rate limited, waiting ${info.waitMs}ms`);
    },
  }
);

const agent = new Agent({ provider });
```

### Standalone Rate Limiter

```typescript
import { RateLimiter } from '@compilr-dev/agents';

const limiter = new RateLimiter({
  maxRequestsPerMinute: 60,
  maxTokensPerMinute: 100000,
});

// Check before making requests
await limiter.waitForCapacity();

// Record usage after requests
limiter.recordRequest(1500); // tokens used

// Check current state
console.log(`Requests remaining: ${limiter.getAvailableRequests()}`);
console.log(`Tokens remaining: ${limiter.getAvailableTokens()}`);
```

## Usage Tracking

Track token usage across agent sessions:

```typescript
import { Agent, ClaudeProvider } from '@compilr-dev/agents';

const agent = new Agent({
  provider: new ClaudeProvider({ apiKey: process.env.ANTHROPIC_API_KEY }),
  usage: {
    enabled: true,
    warnThresholds: {
      inputTokens: 100000,
      outputTokens: 50000,
    },
    onWarning: (warning) => {
      console.log(`Usage warning: ${warning.metric} at ${warning.currentValue}`);
    },
  },
});

// After running the agent
const result = await agent.run('Hello!');

// Get usage stats
const usage = agent.getUsage();
console.log(`Input tokens: ${usage.inputTokens}`);
console.log(`Output tokens: ${usage.outputTokens}`);
console.log(`Total tokens: ${usage.totalTokens}`);
console.log(`Requests: ${usage.requests}`);
```

## Rehearsal System (Impact Analysis)

Rehearsal analyzes potentially destructive operations before execution, showing what files and git state would be affected:

```typescript
import { Agent, ClaudeProvider } from '@compilr-dev/agents';

const agent = new Agent({
  provider: new ClaudeProvider({ apiKey: process.env.ANTHROPIC_API_KEY }),
  rehearsal: {
    enabled: true,
    gitAnalysis: true,      // Analyze git impact
    fileAnalysis: true,     // Analyze file impact
    autoConfirm: false,     // Require user confirmation
    workingDirectory: '/path/to/project',
    onRehearsalComplete: async (result) => {
      console.log('=== Rehearsal Report ===');
      console.log(`Files affected: ${result.files?.filesAffected || 0}`);
      console.log(`Git impact: ${result.git?.summary || 'None'}`);

      // Return true to proceed, false to cancel
      return await askUserConfirmation('Proceed with these changes?');
    },
  },
});

// Destructive operations trigger rehearsal automatically
await agent.run('Delete all .log files and reset the git branch');
```

### Rehearsal Report

The rehearsal system provides detailed impact analysis:

```typescript
interface RehearsalResult {
  files?: {
    filesAffected: number;
    deletions: string[];
    modifications: string[];
    creations: string[];
    totalSizeImpact: number;
  };
  git?: {
    hasUncommittedChanges: boolean;
    uncommittedFiles: string[];
    branchesAffected: string[];
    commitsAffected: number;
    summary: string;
  };
  riskLevel: 'low' | 'medium' | 'high' | 'critical';
  warnings: string[];
}
```

## Task Tool (Sub-Agents)

Spawn specialized sub-agents for complex tasks:

```typescript
import { Agent, ClaudeProvider, createTaskTool } from '@compilr-dev/agents';

const taskTool = createTaskTool({
  provider: new ClaudeProvider({ apiKey: process.env.ANTHROPIC_API_KEY }),
  agentTypes: {
    explore: {
      systemPrompt: 'You are a code exploration expert.',
      tools: ['read_file', 'glob', 'grep'],
      contextMode: 'full',  // Inherit full conversation context
    },
    'code-review': {
      systemPrompt: 'You are a code reviewer.',
      tools: ['read_file', 'grep'],
      contextMode: 'summary',  // Get summarized context
    },
    refactor: {
      systemPrompt: 'You are a refactoring expert.',
      tools: ['read_file', 'write_file', 'edit'],
      contextMode: 'none',  // No inherited context
    },
  },
  defaultThoroughness: 'medium',  // 'quick' | 'medium' | 'thorough'
  maxConcurrentTasks: 3,
});

agent.registerTool(taskTool);

// The LLM can now spawn sub-agents:
// task({ agentType: 'explore', prompt: 'Find all React components' })
```

### Built-in Agent Types

| Type | Purpose | Default Tools |
|------|---------|---------------|
| `explore` | Codebase exploration | glob, grep, read_file |
| `code-review` | Code quality review | read_file, grep |
| `refactor` | Code refactoring | read_file, write_file, edit |
| `test-runner` | Running tests | bash, read_file |
| `doc-lookup` | Documentation search | read_file, grep, web_fetch |
| `debug` | Debugging assistance | read_file, grep, bash |
| `security-audit` | Security analysis | read_file, grep |
| `plan` | Task planning | read_file, glob |
| `general` | General purpose | All tools |

## Hooks System

Extend agent behavior with lifecycle hooks:

```typescript
import { Agent, ClaudeProvider, HooksManager } from '@compilr-dev/agents';

const hooks = new HooksManager();

// Before each LLM call
hooks.register('beforeChat', async (context) => {
  console.log(`Sending ${context.messages.length} messages`);
  // Modify messages if needed
  return { messages: context.messages };
});

// After each LLM response
hooks.register('afterChat', async (context) => {
  console.log(`Received: ${context.response.text?.slice(0, 50)}...`);
});

// Before tool execution
hooks.register('beforeToolCall', async (context) => {
  console.log(`Calling ${context.toolName} with`, context.input);
  // Return { skip: true } to skip execution
});

// After tool execution
hooks.register('afterToolCall', async (context) => {
  console.log(`${context.toolName} returned:`, context.result);
  // Modify result if needed
  return { result: context.result };
});

const agent = new Agent({
  provider: new ClaudeProvider({ apiKey: process.env.ANTHROPIC_API_KEY }),
  hooks,
});
```

## Skills

Skills are reusable prompt templates that enhance agent capabilities:

```typescript
import { Agent, ClaudeProvider, SkillsManager, BUILTIN_SKILLS } from '@compilr-dev/agents';

// Use built-in skills
const skills = new SkillsManager({
  skills: BUILTIN_SKILLS,  // code-review, debug, explain, refactor, planning, security-review
});

const agent = new Agent({
  provider: new ClaudeProvider({ apiKey: process.env.ANTHROPIC_API_KEY }),
  skills,
});

// Invoke a skill
const result = await agent.run('/skill code-review src/auth.ts');
```

### Custom Skills

```typescript
const customSkills = new SkillsManager({
  skills: [
    {
      name: 'optimize',
      description: 'Optimize code for performance',
      prompt: `Analyze the following code and suggest performance optimizations:
- Identify bottlenecks
- Suggest algorithmic improvements
- Recommend caching strategies
- Consider memory usage`,
      tags: ['performance', 'optimization'],
    },
  ],
});
```

### Built-in Skills

| Skill | Description |
|-------|-------------|
| `code-review` | Comprehensive code review with quality, security, and style feedback |
| `debug` | Step-by-step debugging assistance |
| `explain` | Clear explanations of code functionality |
| `refactor` | Refactoring suggestions with clean code principles |
| `planning` | Task breakdown and implementation planning |
| `security-review` | Security vulnerability analysis |

## Tracing & Logging

Monitor agent execution with structured logging:

```typescript
import { Agent, ClaudeProvider, TracingManager } from '@compilr-dev/agents';

const tracing = new TracingManager({
  enabled: true,
  logLevel: 'info',  // 'debug' | 'info' | 'warn' | 'error'
  destination: 'console',  // or 'file' or custom function
  filePath: './agent-logs.jsonl',
  includeTimestamps: true,
  redactPatterns: [/api[_-]?key/i, /password/i],  // Redact sensitive data
});

const agent = new Agent({
  provider: new ClaudeProvider({ apiKey: process.env.ANTHROPIC_API_KEY }),
  tracing,
});

// Logs include:
// - LLM requests/responses
// - Tool calls and results
// - Errors and warnings
// - Timing information
```

### OpenTelemetry Integration

```typescript
import { createOtelTracing } from '@compilr-dev/agents';

// Export traces to your observability platform
const tracing = createOtelTracing({
  serviceName: 'my-agent',
  endpoint: 'http://localhost:4318/v1/traces',
});

const agent = new Agent({ provider, tracing });
```

## Requirements

- **Node.js** 18 or higher
- **API Key** for your chosen provider (except Ollama)

## Peer Dependencies

- `@anthropic-ai/sdk` (optional, for Claude)
- `@modelcontextprotocol/sdk` (optional, for MCP)

## Design Philosophy

1. **Minimal dependencies**: Only `@anthropic-ai/sdk` and `@modelcontextprotocol/sdk` as optional peer deps
2. **Type safety**: Full TypeScript support with strict mode
3. **Extensibility**: Easy to add new providers and tools
4. **Testability**: MockProvider for easy unit testing
5. **Real-time feedback**: Event system for CLI applications

## Related Packages

- [@compilr-dev/cli](https://www.npmjs.com/package/@compilr-dev/cli) - AI-powered CLI assistant
- [@compilr-dev/agents-coding](https://www.npmjs.com/package/@compilr-dev/agents-coding) - Coding-specific tools (git, runners, code search)

## Links

- [Website](https://compilr.dev)
- [npm Package](https://www.npmjs.com/package/@compilr-dev/agents)
- [Report Issues](https://github.com/compilr-dev/agents/issues)

## License

[FSL-1.1-MIT](https://fsl.software/) - See [LICENSE](LICENSE) for details. Converts to MIT after 2 years per version.

---

<p align="center">
  <strong>Built with care by <a href="https://compilr.dev">compilr.dev</a></strong>
</p>
