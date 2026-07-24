---
title: "AgentConfig"
parent: Interfaces
nav_order: 1
---


# Interface: AgentConfig

Defined in: agent.ts:187

Agent configuration options

## Properties

### ~~anchors?~~

```ts
optional anchors?: AnchorManagerOptions;
```

Defined in: agent.ts:438

#### Deprecated

Use `pins` instead

### autoCheckpoint?

```ts
optional autoCheckpoint?: boolean;
```

Defined in: agent.ts:398

Automatically save state after each run() call.
Requires checkpointer to be set. Default: false.

### autoContextManagement?

```ts
optional autoContextManagement?: boolean;
```

Defined in: agent.ts:316

Enable automatic context management (compaction, summarization).
Requires contextManager to be set. Default: true when contextManager is provided.

### chatOptions?

```ts
optional chatOptions?: ChatOptions;
```

Defined in: agent.ts:292

Chat options (model, temperature, etc.)

### checkpointer?

```ts
optional checkpointer?: Checkpointer;
```

Defined in: agent.ts:386

Checkpointer for persisting agent state.
If provided, enables checkpoint() and resume() functionality.

### checkpointOnAbort?

```ts
optional checkpointOnAbort?: boolean;
```

Defined in: agent.ts:408

Save a partial checkpoint when run is aborted or encounters an error.
This allows recovery from interrupted runs.
Requires checkpointer to be set. Default: false.

Inspired by LangGraph issue #5672: Cancellation causes loss of
streamed state not yet persisted as checkpoint.

### compactToolResults?

```ts
optional compactToolResults?: boolean;
```

Defined in: agent.ts:337

Use compact text format for tool results in LLM messages.
Strips JSON wrappers and metadata, reducing token usage.
Enabled by default when contextManager is provided. Set to `false` to disable.

### contextManager?

```ts
optional contextManager?: ContextManager;
```

Defined in: agent.ts:310

Context manager for tracking and managing context window usage.
If not provided, context management is disabled.

### deadMessagePruning?

```ts
optional deadMessagePruning?: false | Partial<PruneConfig>;
```

Defined in: agent.ts:343

Dead message pruning configuration. Prunes superseded errors and permission exchanges.
Enabled by default when contextManager is provided. Set to `false` to disable.

### delegation?

```ts
optional delegation?: DelegationConfig;
```

Defined in: agent.ts:669

Tool result delegation config. When set and enabled, large tool results
are automatically summarized to conserve context tokens. Full results are
stored in-memory for optional recall via `recall_full_result`.

#### Example

```typescript
const agent = new Agent({
  provider,
  delegation: {
    enabled: true,
    delegationThreshold: 8000, // tokens above which to delegate
    strategy: 'auto',         // try LLM, fall back to extractive
    toolOverrides: {
      bash: { threshold: 12000 },
      grep: { threshold: 4000 },
    },
  },
});
```

### enableFileTracking?

```ts
optional enableFileTracking?: boolean;
```

Defined in: agent.ts:699

Enable file access tracking for context restoration hints.

When enabled, the agent tracks which files were read, referenced (grep/glob),
and modified during execution. After context compaction, these hints are
injected to help the LLM understand what files it previously accessed.

Requires contextManager to be set (hints are injected after compaction).

#### Default

```ts
false
```

#### Example

```typescript
const agent = new Agent({
  provider,
  contextManager: new ContextManager({ provider }),
  enableFileTracking: true, // Automatically track file accesses
});

// After compaction, the agent will inject hints like:
// [Context compacted. Previously accessed files:]
// Read (3 files): file1.ts (100 lines), file2.ts (50 lines)...
```

### fileRestoration?

```ts
optional fileRestoration?: {
  maxInlineTokens?: number;
};
```

Defined in: agent.ts:710

Options for file context restoration after compaction.

Controls how file contents are re-injected into the context after
compaction. Small files get their content inlined; large files get
reference-only hints.

Only applies when `enableFileTracking` is true.

#### maxInlineTokens?

```ts
optional maxInlineTokens?: number;
```

Max total tokens for inline file content after compaction (default: 4000)

### guardrails?

```ts
optional guardrails?: GuardrailManagerOptions;
```

Defined in: agent.ts:477

Guardrail options for pattern-based safety checks.

Guardrails scan tool inputs before execution and can:
- warn: Log a warning but proceed
- confirm: Require confirmation (via onTriggered handler)
- block: Prevent execution entirely

#### Example

```typescript
const agent = new Agent({
  provider,
  guardrails: {
    enabled: true,
    includeDefaults: true, // Include built-in guardrails
    custom: [
      {
        id: 'no-prod',
        name: 'Production Protection',
        description: 'Block operations on production',
        patterns: [/prod/i],
        action: 'block',
        message: 'Production operations are blocked',
      }
    ],
    onTriggered: async (result, context) => {
      // Return true to proceed, false to block
      return await askUser(result.guardrail.message);
    }
  }
});
```

### hooks?

```ts
optional hooks?: HooksConfig;
```

Defined in: agent.ts:642

Hooks for customizing agent behavior at various lifecycle points.

Hooks provide extension points without subclassing for:
- Logging and tracing
- Input/output transformation
- Custom validation
- Metrics collection
- Integration with external systems

#### Example

```typescript
const agent = new Agent({
  provider,
  hooks: {
    beforeTool: [
      async (ctx) => {
        console.log(`Tool ${ctx.toolName} starting...`);
      }
    ],
    afterTool: [
      async (ctx) => {
        console.log(`Tool ${ctx.toolName} completed in ${ctx.durationMs}ms`);
        // Optionally modify result
        return { result: ctx.result };
      }
    ],
    beforeLLM: [
      async (ctx) => {
        // Optionally inject or transform messages
        return { messages: ctx.messages };
      }
    ],
    onError: [
      async (ctx) => {
        console.error(`Error in ${ctx.phase}:`, ctx.error);
      }
    ]
  }
});
```

### iterationLimitBehavior?

```ts
optional iterationLimitBehavior?: "summarize" | "error" | "continue";
```

Defined in: agent.ts:238

Behavior when max iterations is reached (default: 'error').
- 'error': Throw MaxIterationsError immediately
- 'summarize': Generate a final summary response before throwing
- 'continue': Return partial result without throwing (response will be empty)

Note: If onIterationLimitReached callback is provided, it takes precedence.

### logger?

```ts
optional logger?: Logger;
```

Defined in: agent.ts:730

Logger instance for structured diagnostic logging.
When omitted, no logging is performed.

#### Example

```typescript
import { createLogger } from '@compilr-dev/logger';
const log = createLogger({ package: 'my-app' });
const agent = new Agent({ provider, logger: log });
```

### maxConsecutiveToolCalls?

```ts
optional maxConsecutiveToolCalls?: number;
```

Defined in: agent.ts:211

Maximum consecutive identical tool calls (same name + input + result) before
the loop detector trips (default: 5). Set to 0 to disable loop detection.

Detection is result-aware: a repeated call only counts when its result is
also identical to the previous one, so legitimate polling that returns
changing output (e.g. `bash_output` while a build runs) does not trip.

### maxIterations?

```ts
optional maxIterations?: number;
```

Defined in: agent.ts:201

Maximum iterations for tool use loops (default: 10)

### maxToolLoopNudges?

```ts
optional maxToolLoopNudges?: number;
```

Defined in: agent.ts:228

On a loop trip, how many times to inject a corrective "self-heal" message
and let the agent continue before throwing ToolLoopError (default: 1).
Set to 0 to throw immediately on the first trip (no self-heal).

Ignored when `onToolLoopDetected` is provided (that callback takes over).

### observationMask?

```ts
optional observationMask?: 
  | false
| Partial<ObservationMaskConfig>;
```

Defined in: agent.ts:322

Observation masking configuration. Masks old tool results in history to reduce tokens.
Enabled by default when contextManager is provided. Set to `false` to disable.

### onEvent?

```ts
optional onEvent?: AgentEventHandler;
```

Defined in: agent.ts:348

Event handler for monitoring agent execution

### onIterationLimitReached?

```ts
optional onIterationLimitReached?: (context) => Promise<number | false>;
```

Defined in: agent.ts:261

Callback invoked when the agent reaches its iteration limit.
Allows the caller to decide whether to continue or stop.

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `context` | \{ `iteration`: `number`; `maxIterations`: `number`; `toolCallCount`: `number`; \} | Information about the current state |
| `context.iteration` | `number` | - |
| `context.maxIterations` | `number` | - |
| `context.toolCallCount` | `number` | - |

#### Returns

`Promise`\<`number` \| `false`\>

Promise resolving to:
  - `false` to stop the agent gracefully
  - A positive number to continue with that many additional iterations

If this callback is provided and returns a number, the agent will continue
running with the extended iteration limit. This takes precedence over
iterationLimitBehavior.

#### Example

```typescript
onIterationLimitReached: async ({ iteration, toolCallCount }) => {
  const answer = await askUser(`Agent used ${iteration} iterations. Continue?`);
  return answer === 'yes' ? 50 : false; // Add 50 more or stop
}
```

### onToolLoopDetected?

```ts
optional onToolLoopDetected?: (context) => Promise<boolean>;
```

Defined in: agent.ts:283

Callback when tool loop is detected (same tool called N times with identical input).

When provided, the agent asks the user instead of throwing ToolLoopError.
Return `true` to continue (reset the counter), `false` to stop.

When not provided, ToolLoopError is thrown (backwards compatible).

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `context` | \{ `consecutiveCalls`: `number`; `input`: `Record`\<`string`, `unknown`\>; `toolName`: `string`; \} |
| `context.consecutiveCalls` | `number` |
| `context.input` | `Record`\<`string`, `unknown`\> |
| `context.toolName` | `string` |

#### Returns

`Promise`\<`boolean`\>

#### Example

```typescript
onToolLoopDetected: async ({ toolName, consecutiveCalls }) => {
  const answer = await askUser(`${toolName} called ${consecutiveCalls} times. Continue?`);
  return answer === 'yes';
}
```

### permissionManager?

```ts
optional permissionManager?: PermissionManager;
```

Defined in: agent.ts:521

Pre-existing PermissionManager instance.

Use this to share a PermissionManager between agents (e.g., parent and sub-agents).
When provided, takes precedence over `permissions` options.

This is primarily used internally for sub-agent permission inheritance.

### permissions?

```ts
optional permissions?: PermissionManagerOptions;
```

Defined in: agent.ts:511

Permission options for tool-level access control.

Permissions allow fine-grained control over which tools can execute
and when user approval is required.

#### Example

```typescript
const agent = new Agent({
  provider,
  permissions: {
    defaultLevel: 'always', // Default: allow all tools
    rules: [
      { toolName: 'bash', level: 'once', description: 'Shell commands' },
      { toolName: 'write_file', level: 'session', description: 'File writes' },
      { toolName: 'delete_*', level: 'deny' }, // Wildcard: block all delete tools
    ],
    onPermissionRequest: async (request) => {
      // Return true to allow, false to deny
      return await showConfirmDialog(
        `Allow ${request.toolName}?`,
        request.preview
      );
    }
  }
});
```

### pins?

```ts
optional pins?: AnchorManagerOptions;
```

Defined in: agent.ts:435

Pin manager options for critical information that survives context compaction.

Pins are pieces of information that:
- Never get compacted - Survive all context management
- Always re-injected - Present in every LLM call
- Scoped - Session, persistent, or temporary

#### Example

```typescript
const agent = new Agent({
  provider,
  pins: {
    maxAnchors: 20,
    maxTokens: 2000,
    persistPath: '~/.myapp/anchors.json',
    includeDefaults: true, // Include built-in safety anchors
  }
});
```

### projectMemory?

```ts
optional projectMemory?: ProjectMemory;
```

Defined in: agent.ts:557

Pre-loaded project memory to prepend to system prompt.

Use `Agent.createWithMemory()` to automatically load from files,
or pass a pre-loaded ProjectMemory object.

#### Example

```typescript
// Option 1: Use the factory method (recommended)
const agent = await Agent.createWithMemory({
  provider,
  systemPrompt: 'You are a helpful assistant.',
  projectMemoryOptions: {
    providers: ['claude', 'gemini'],
    includeGeneric: true,
  },
  projectMemoryDir: '/path/to/project',
});

// Option 2: Pre-load memory manually
const loader = new ProjectMemoryLoader({ providers: 'claude' });
const memory = await loader.load('/path/to/project');

const agent = new Agent({
  provider,
  systemPrompt: 'You are a helpful assistant.',
  projectMemory: memory, // Pre-loaded memory
});
```

### provider

```ts
provider: LLMProvider;
```

Defined in: agent.ts:191

The LLM provider to use

### retry?

```ts
optional retry?: LLMRetryConfig;
```

Defined in: agent.ts:376

Configuration for automatic retry on transient LLM errors.
Enabled by default with sensible defaults (10 attempts, exponential backoff).

Retryable errors include:
- Rate limit (429)
- Server errors (5xx)
- Connection/network errors
- Anthropic overloaded (529)

#### Example

```typescript
const agent = new Agent({
  provider,
  retry: {
    maxAttempts: 5,      // Max 5 retries
    baseDelayMs: 2000,   // Start with 2s delay
    maxDelayMs: 60000,   // Cap at 60s
  }
});
```

### sessionId?

```ts
optional sessionId?: string;
```

Defined in: agent.ts:392

Session ID for this agent instance.
If not provided, a new session ID is generated automatically.

### systemPrompt?

```ts
optional systemPrompt?: string;
```

Defined in: agent.ts:196

System prompt for the agent

### textRepetitionDetection?

```ts
optional textRepetitionDetection?: boolean;
```

Defined in: agent.ts:219

Detect text-degeneration loops mid-stream (a model repeating the same
sentence/paragraph forever, typically after an unrecoverable tool error)
and stop the generation, emitting `text_repetition_detected`. Default: true.
Set false to disable (the output-token cap is then the only backstop).

### toolRegistry?

```ts
optional toolRegistry?: ToolRegistry;
```

Defined in: agent.ts:297

Custom tool registry (optional, creates new one if not provided)

### toolTimeoutMs?

```ts
optional toolTimeoutMs?: number;
```

Defined in: agent.ts:304

Default timeout for tool execution in milliseconds (default: 30000 = 30s).
Set to 0 to disable timeout. Only used when toolRegistry is not provided.
Sub-agents inherit this timeout from the parent agent.

### usage?

```ts
optional usage?: UsageTrackerOptions;
```

Defined in: agent.ts:594

Usage tracking options for monitoring token usage.

Note: We track tokens only, not dollar costs. Pricing changes frequently
and providing potentially inaccurate cost information would be misleading.

#### Example

```typescript
const agent = new Agent({
  provider,
  usage: {
    enabled: true,
    budget: {
      maxTotalTokens: 100000,  // 100k token limit
      warningThreshold: 0.8,   // Warn at 80%
    },
  },
});

// After runs, check usage
console.log(agent.getUsageStats());
console.log(agent.getTotalTokens());

// Listen for budget events
agent.onEvent((event) => {
  if (event.type === 'usage_budget_warning') {
    console.log('Budget warning!', event.status);
  }
});
```

### windowing?

```ts
optional windowing?: false | Partial<WindowingConfig>;
```

Defined in: agent.ts:330

Smart windowing configuration. Programmatically compacts old messages when
history exceeds a token budget. Three zones: recent (intact), middle
(truncated), old (event log). Zero LLM calls.
Enabled by default when contextManager is provided. Set to `false` to disable.
