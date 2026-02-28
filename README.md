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

> [!WARNING]
> This package is in beta. APIs may change between minor versions.

## Features

- **Multi-LLM Support** - 9 providers: Claude, OpenAI, Gemini, Ollama (local), Together AI, Groq, Fireworks, Perplexity, OpenRouter
- **17 Built-in Tools** - File ops, bash, grep, glob, edit, web fetch, sub-agents, todos, backlog, and more
- **Sub-agents** - Spawn specialized agents for complex tasks (9 built-in agent types)
- **Context Management** - Token budgeting, compaction, summarization
- **11 Skills** - Reusable prompts for common workflows
- **Safety Features** - Permissions, 15 built-in guardrails, anchors, rehearsal mode
- **Streaming** - Real-time event streaming with abort support
- **Hooks System** - Lifecycle hooks (beforeChat, afterChat, beforeToolCall, afterToolCall)
- **MCP Integration** - Load tools from MCP servers
- **Project Memory** - Auto-loads CLAUDE.md, GEMINI.md, CURSOR.md, and more

## Quick Start

```bash
npm install @compilr-dev/agents
```

```typescript
import { Agent, ClaudeProvider } from '@compilr-dev/agents';

const agent = new Agent({
  provider: new ClaudeProvider({ apiKey: process.env.ANTHROPIC_API_KEY }),
  systemPrompt: 'You are a helpful assistant.',
});

for await (const event of agent.run('Hello!')) {
  if (event.type === 'text') {
    process.stdout.write(event.content);
  }
}
```

## LLM Providers

```typescript
import {
  ClaudeProvider,      // Anthropic Claude
  OpenAIProvider,      // OpenAI GPT
  GeminiProvider,      // Google Gemini
  OllamaProvider,      // Local models (no API key)
  TogetherProvider,    // Together AI
  GroqProvider,        // Groq (fast inference)
  FireworksProvider,   // Fireworks AI
  PerplexityProvider,  // Perplexity (search-augmented)
  OpenRouterProvider,  // OpenRouter (multi-provider)
} from '@compilr-dev/agents';

// Claude (recommended)
new ClaudeProvider({ apiKey: 'sk-ant-...' });

// OpenAI
new OpenAIProvider({ apiKey: 'sk-...' });

// Gemini
new GeminiProvider({ apiKey: '...' });

// Ollama (local, no API key)
new OllamaProvider({ model: 'llama3' });
```

## Built-in Tools

| Tool | Description |
|------|-------------|
| `readFile` | Read file contents |
| `writeFile` | Write to files |
| `edit` | Edit files with search/replace |
| `bash` | Execute shell commands |
| `bashOutput` | Get output from background shell |
| `killShell` | Terminate background shell |
| `grep` | Search file contents |
| `glob` | Find files by pattern |
| `todoWrite` | Manage task list |
| `todoRead` | Read task list |
| `backlogRead` | Read backlog items |
| `backlogWrite` | Manage backlog items |
| `webFetch` | Fetch URL content |
| `task` | Spawn sub-agents |
| `suggest` | Get action suggestions |
| `askUser` | Ask user questions |
| `askUserSimple` | Simple yes/no prompts |

## Sub-agents (Task Tool)

Spawn specialized agents for complex tasks:

```typescript
import { createTaskTool } from '@compilr-dev/agents';

const taskTool = createTaskTool({
  provider,
  agentTypes: {
    explore: { description: 'Explore codebase', systemPrompt: '...' },
    'code-review': { description: 'Review code', systemPrompt: '...' },
    plan: { description: 'Create plans', systemPrompt: '...' },
  },
});
```

**Built-in agent types:** explore, code-review, general, plan, test-runner, doc-lookup, refactor, security-audit, debug

## Context Management

Manage token budgets and prevent context overflow:

```typescript
import { ContextManager } from '@compilr-dev/agents';

const contextManager = new ContextManager({
  maxTokens: 100000,
  budgets: {
    system: 0.15,
    anchors: 0.10,
    conversation: 0.75,
  },
});
```

## Skills

Reusable prompts for common workflows:

```typescript
import { SkillRegistry, defaultSkills } from '@compilr-dev/agents';

const skills = new SkillRegistry();
defaultSkills.forEach(skill => skills.register(skill));

const prompt = skills.invoke('code-review', { focus: 'security' });
```

**Built-in skills:** code-review, debug, explain, refactor, planning, security-review, design, refine, sketch, build, scaffold

## Safety Features

### Permissions

```typescript
import { PermissionManager } from '@compilr-dev/agents';

const permissions = new PermissionManager();
permissions.setPermission('bash', 'once'); // Ask each time
permissions.setPermission('writeFile', 'session'); // Ask once per session
```

**Permission levels:** always, session, once, deny (with wildcard patterns)

### Guardrails

```typescript
import { defaultGuardrails } from '@compilr-dev/agents';
// 15 built-in patterns for secrets, PII, dangerous commands, etc.
```

### Anchors

```typescript
import { AnchorManager } from '@compilr-dev/agents';
// Keep critical information across context compaction
```

## Requirements

- **Node.js** 20 or higher
- **API Key** for your chosen provider (except Ollama)

## Peer Dependencies

- `@anthropic-ai/sdk` (optional, for Claude)
- `@modelcontextprotocol/sdk` (optional, for MCP)

## Related Packages

- [@compilr-dev/cli](https://www.npmjs.com/package/@compilr-dev/cli) - AI-powered CLI assistant
- [@compilr-dev/agents-coding](https://www.npmjs.com/package/@compilr-dev/agents-coding) - Coding-specific tools

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
