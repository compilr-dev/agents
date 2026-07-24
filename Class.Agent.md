---
title: "Agent"
parent: Classes
nav_order: 1
---


# Class: Agent

Defined in: agent.ts:1036

@compilr-dev/agents

Lightweight multi-LLM agent library for building CLI AI assistants

## Constructors

### Constructor

```ts
new Agent(config): Agent;
```

Defined in: agent.ts:1143

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `config` | [`AgentConfig`](Interface.AgentConfig.md) |

#### Returns

`Agent`

## Accessors

### sessionId

#### Get Signature

```ts
get sessionId(): string;
```

Defined in: agent.ts:1384

Get the session ID for this agent instance

##### Returns

`string`

## Methods

### ~~addAnchor()~~

```ts
addAnchor(input): Anchor | undefined;
```

Defined in: agent.ts:1649

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `input` | [`AnchorInput`](Interface.AnchorInput.md) |

#### Returns

[`Anchor`](Interface.Anchor.md) \| `undefined`

#### Deprecated

Use addPin() instead

### addGuardrail()

```ts
addGuardrail(input): Guardrail | undefined;
```

Defined in: agent.ts:1704

Add a custom guardrail

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `input` | [`GuardrailInput`](Interface.GuardrailInput.md) | Guardrail definition |

#### Returns

[`Guardrail`](Interface.Guardrail.md) \| `undefined`

The created guardrail, or undefined if guardrails are not enabled

#### Example

```typescript
agent.addGuardrail({
  id: 'no-delete-important',
  name: 'Important Files Protection',
  description: 'Prevent deletion of important files',
  patterns: [/rm.*important/i, /delete.*important/i],
  action: 'block',
  message: 'Cannot delete files marked as important',
  scope: ['bash'],
});
```

### addPermission()

```ts
addPermission(rule): this;
```

Defined in: agent.ts:1783

Add a permission rule for a tool

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `rule` | [`ToolPermission`](Interface.ToolPermission.md) | Permission rule to add |

#### Returns

`this`

this for chaining

#### Example

```typescript
agent.addPermission({
  toolName: 'bash',
  level: 'once',
  description: 'Execute shell commands',
});
```

### addPin()

```ts
addPin(input): Anchor | undefined;
```

Defined in: agent.ts:1534

Add a pin (critical information that survives context compaction).

Pins are injected into every LLM call and never get compacted.
Use them for information that must not be forgotten.

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `input` | [`AnchorInput`](Interface.AnchorInput.md) | Pin input (uses AnchorInput type) |

#### Returns

[`Anchor`](Interface.Anchor.md) \| `undefined`

The created pin, or undefined if pins are not enabled

#### Example

```typescript
agent.addPin({
  content: 'Team roster: $default, $arch',
  priority: 'info',
  scope: 'session',
});
```

### checkpoint()

```ts
checkpoint(metadata?): Promise<string>;
```

Defined in: agent.ts:2335

Save the current state using the configured checkpointer.
Throws if no checkpointer is configured.

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `metadata?` | `Partial`\<[`SessionMetadata`](Interface.SessionMetadata.md)\> | Optional metadata overrides |

#### Returns

`Promise`\<`string`\>

The session ID

#### Example

```typescript
const agent = new Agent({
  provider,
  checkpointer: new FileCheckpointer('~/.myapp/sessions/'),
});

await agent.run('Hello!');
const sessionId = await agent.checkpoint();
console.log(`Saved as: ${sessionId}`);
```

### ~~clearAnchors()~~

```ts
clearAnchors(options?): number;
```

Defined in: agent.ts:1669

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `options?` | [`AnchorClearOptions`](Interface.AnchorClearOptions.md) |

#### Returns

`number`

#### Deprecated

Use clearPins() instead

### clearHistory()

```ts
clearHistory(): this;
```

Defined in: agent.ts:1931

Clear conversation history to start fresh

#### Returns

`this`

### clearPins()

```ts
clearPins(options?): number;
```

Defined in: agent.ts:1584

Clear pins based on criteria

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `options?` | [`AnchorClearOptions`](Interface.AnchorClearOptions.md) | Clear options for filtering which pins to remove |

#### Returns

`number`

Number of pins removed

### clearSessionPermissions()

```ts
clearSessionPermissions(): this;
```

Defined in: agent.ts:1846

Clear all session-level permissions

#### Returns

`this`

### compact()

```ts
compact(options?): Promise<{
  categoryStats?: Record<ContextCategory, {
     action: "preserved" | "compacted" | "summarized";
     tokensAfter: number;
     tokensBefore: number;
  }>;
  filesCreated?: string[];
  messagesPreserved: number;
  originalTokens: number;
  restorationHintsInjected: boolean;
  rounds: number;
  success: boolean;
  summary: string;
  summaryTokens: number;
  toolResultsRepaired: number;
}>;
```

Defined in: agent.ts:2105

Compact the conversation context to reduce token usage.

This is the recommended way to trigger context compaction externally.
It handles:
1. Summarizing older messages
2. Repairing tool use/result pairing (prevents API errors)
3. Injecting context restoration hints (if file tracking is enabled)
4. Updating the conversation history

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `options?` | \{ `emergency?`: `boolean`; `injectRestorationHints?`: `boolean`; `targetUtilization?`: `number`; `useSmartCompaction?`: `boolean`; \} | Compaction options |
| `options.emergency?` | `boolean` | Use emergency mode (more aggressive summarization). Default: auto-detect based on context utilization |
| `options.injectRestorationHints?` | `boolean` | Inject file restoration hints after compaction. Only applies if file tracking is enabled. Default: true (if file tracking is enabled) |
| `options.targetUtilization?` | `number` | Target utilization after compaction (0-1). Default: from context manager config (typically 0.5) |
| `options.useSmartCompaction?` | `boolean` | Use smart category-aware compaction instead of simple summarization. Smart compaction: - Preserves system and recent messages completely - Saves large tool results to files - Summarizes history with LLM Default: true |

#### Returns

`Promise`\<\{
  `categoryStats?`: `Record`\<[`ContextCategory`](TypeAlias.ContextCategory.md), \{
     `action`: `"preserved"` \| `"compacted"` \| `"summarized"`;
     `tokensAfter`: `number`;
     `tokensBefore`: `number`;
  \}\>;
  `filesCreated?`: `string`[];
  `messagesPreserved`: `number`;
  `originalTokens`: `number`;
  `restorationHintsInjected`: `boolean`;
  `rounds`: `number`;
  `success`: `boolean`;
  `summary`: `string`;
  `summaryTokens`: `number`;
  `toolResultsRepaired`: `number`;
\}\>

Compaction result with statistics

#### Example

```typescript
// Basic compaction
const result = await agent.compact();
console.log(`Reduced from ${result.originalTokens} to ${result.summaryTokens} tokens`);

// Compaction without restoration hints
await agent.compact({ injectRestorationHints: false });

// Emergency compaction (more aggressive)
await agent.compact({ emergency: true });
```

### createSubAgent()

```ts
createSubAgent(config): this;
```

Defined in: agent.ts:2519

Create and register a sub-agent with isolated context.

Sub-agents are specialized agents that handle discrete tasks independently.
They have their own context window and can have different tools/permissions.

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `config` | [`SubAgentConfig`](Interface.SubAgentConfig.md) |

#### Returns

`this`

#### Example

```typescript
agent.createSubAgent({
  name: 'code-reviewer',
  description: 'Reviews code for security and quality issues',
  systemPrompt: 'You are a code review specialist...',
  tools: [readFileTool], // Restricted tools
  contextMode: 'isolated',
});

const result = await agent.runSubAgent('code-reviewer', 'Review src/auth.ts');
```

### createWithMemory()

```ts
static createWithMemory(
   config, 
   memoryOptions?, 
memoryDir?): Promise<Agent>;
```

Defined in: agent.ts:1363

Create an agent with project memory loaded from files.

This factory method automatically discovers and loads project-specific
instructions from files like CLAUDE.md, GEMINI.md, PROJECT.md, etc.

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `config` | `Omit`\<[`AgentConfig`](Interface.AgentConfig.md), `"projectMemory"`\> | Agent configuration |
| `memoryOptions?` | [`ProjectMemoryOptions`](Interface.ProjectMemoryOptions.md) | Project memory loading options |
| `memoryDir?` | `string` | Directory to search for memory files (defaults to cwd) |

#### Returns

`Promise`\<`Agent`\>

Agent instance with loaded project memory

#### Example

```typescript
// Load Claude-specific instructions
const agent = await Agent.createWithMemory(
  {
    provider,
    systemPrompt: 'You are a helpful assistant.',
  },
  { providers: 'claude' },
  '/path/to/project'
);

// Load instructions for multiple providers
const agent = await Agent.createWithMemory(
  { provider },
  { providers: ['claude', 'gemini'], includeGeneric: true }
);

// Access loaded memory
const memory = agent.getProjectMemory();
console.log(`Loaded ${memory?.files.length} memory files`);
```

### disableGuardrail()

```ts
disableGuardrail(id): boolean;
```

Defined in: agent.ts:1746

Disable a guardrail by ID

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |

#### Returns

`boolean`

### disposeAllSubAgents()

```ts
disposeAllSubAgents(): void;
```

Defined in: agent.ts:2795

Dispose all sub-agents and release their resources.

Useful for cleanup when the parent agent is done or
to free memory during long-running sessions.

#### Returns

`void`

### disposeSubAgent()

```ts
disposeSubAgent(name): boolean;
```

Defined in: agent.ts:2770

Dispose a sub-agent and release its resources.

This clears the sub-agent's:
- Conversation history
- Context manager state
- Tool registry

After disposal, the sub-agent must be re-created to use again.

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `name` | `string` |

#### Returns

`boolean`

### emitCustomEvent()

```ts
emitCustomEvent(config): void;
```

Defined in: agent.ts:1896

Emit a custom event that will be streamed to event handlers.

This allows tools, middleware, and user code to emit custom events
that are streamed alongside built-in agent events.

Inspired by LangGraph's get_stream_writer() pattern.
Addresses issues like LangGraph #6330 (preserve event metadata).

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `config` | [`CustomEventConfig`](Interface.CustomEventConfig.md) | Custom event configuration |

#### Returns

`void`

#### Example

```typescript
agent.emitCustomEvent({
  name: 'progress',
  data: { step: 1, total: 5, message: 'Processing...' },
  metadata: { toolName: 'myTool' },
});
```

### enableGuardrail()

```ts
enableGuardrail(id): boolean;
```

Defined in: agent.ts:1739

Enable a guardrail by ID

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |

#### Returns

`boolean`

### formatRestorationHints()

```ts
formatRestorationHints(): string;
```

Defined in: agent.ts:2034

Format context restoration hints based on tracked file accesses.
Returns empty string if no files have been accessed or file tracking is disabled.

#### Returns

`string`

### fromState()

```ts
static fromState(state, options): Agent;
```

Defined in: agent.ts:2443

Create an agent from a serialized AgentState object.

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `state` | [`AgentState`](Interface.AgentState.md) | The serialized agent state |
| `options` | \{ `checkpointer?`: [`Checkpointer`](Interface.Checkpointer.md); `onEvent?`: [`AgentEventHandler`](TypeAlias.AgentEventHandler.md); `provider`: [`LLMProvider`](Interface.LLMProvider.md); `systemPrompt?`: `string`; `tools?`: [`Tool`](Interface.Tool.md)\<`object`\>[]; \} | Options for the new agent |
| `options.checkpointer?` | [`Checkpointer`](Interface.Checkpointer.md) | - |
| `options.onEvent?` | [`AgentEventHandler`](TypeAlias.AgentEventHandler.md) | - |
| `options.provider` | [`LLMProvider`](Interface.LLMProvider.md) | - |
| `options.systemPrompt?` | `string` | - |
| `options.tools?` | [`Tool`](Interface.Tool.md)\<`object`\>[] | - |

#### Returns

`Agent`

#### Example

```typescript
// Load state from somewhere
const json = await fs.readFile('session.json', 'utf-8');
const state = JSON.parse(json);

// Create agent from state
const agent = Agent.fromState(state, { provider });
await agent.run('Continue...');
```

### ~~getAnchor()~~

```ts
getAnchor(id): Anchor | undefined;
```

Defined in: agent.ts:1653

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |

#### Returns

[`Anchor`](Interface.Anchor.md) \| `undefined`

#### Deprecated

Use getPin() instead

### ~~getAnchorManager()~~

```ts
getAnchorManager(): AnchorManager | undefined;
```

Defined in: agent.ts:1673

#### Returns

[`AnchorManager`](Class.AnchorManager.md) \| `undefined`

#### Deprecated

Use getPinManager() instead

### ~~getAnchors()~~

```ts
getAnchors(options?): Anchor[];
```

Defined in: agent.ts:1657

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `options?` | [`AnchorQueryOptions`](Interface.AnchorQueryOptions.md) |

#### Returns

[`Anchor`](Interface.Anchor.md)[]

#### Deprecated

Use getPins() instead

### getBudgetStatus()

```ts
getBudgetStatus(): BudgetStatus | undefined;
```

Defined in: agent.ts:1471

Get budget status.

#### Returns

[`BudgetStatus`](Interface.BudgetStatus.md) \| `undefined`

### getContextManager()

```ts
getContextManager(): ContextManager | undefined;
```

Defined in: agent.ts:1979

Get the context manager (if configured)

#### Returns

[`ContextManager`](Class.ContextManager.md) \| `undefined`

### getContextStats()

```ts
getContextStats(): ContextStats | undefined;
```

Defined in: agent.ts:1994

Get context statistics

#### Returns

[`ContextStats`](Interface.ContextStats.md) \| `undefined`

### getDeadMessagePruneStats()

```ts
getDeadMessagePruneStats(): 
  | {
  errorsPruned: number;
  permissionsPruned: number;
  prunedCount: number;
  tokensSaved: number;
}
  | undefined;
```

Defined in: agent.ts:2010

Get dead message pruning statistics (errors pruned, permissions pruned, tokens saved).

#### Returns

  \| \{
  `errorsPruned`: `number`;
  `permissionsPruned`: `number`;
  `prunedCount`: `number`;
  `tokensSaved`: `number`;
\}
  \| `undefined`

### getFileTracker()

```ts
getFileTracker(): FileAccessTracker | undefined;
```

Defined in: agent.ts:2026

Get the file access tracker (if file tracking is enabled)

#### Returns

[`FileAccessTracker`](Class.FileAccessTracker.md) \| `undefined`

### getGuardrail()

```ts
getGuardrail(id): Guardrail | undefined;
```

Defined in: agent.ts:1711

Get a guardrail by ID

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |

#### Returns

[`Guardrail`](Interface.Guardrail.md) \| `undefined`

### getGuardrailManager()

```ts
getGuardrailManager(): GuardrailManager | undefined;
```

Defined in: agent.ts:1753

Get the guardrail manager (if configured)

#### Returns

[`GuardrailManager`](Class.GuardrailManager.md) \| `undefined`

### getGuardrails()

```ts
getGuardrails(): Guardrail[];
```

Defined in: agent.ts:1718

Get all guardrails

#### Returns

[`Guardrail`](Interface.Guardrail.md)[]

### getHistory()

```ts
getHistory(): Message[];
```

Defined in: agent.ts:1942

Get the current conversation history

#### Returns

[`Message`](Interface.Message.md)[]

### getModel()

```ts
getModel(): string;
```

Defined in: agent.ts:1609

Get the current model ID for this agent.

#### Returns

`string`

The model ID string (e.g., 'claude-sonnet-4-20250514')

### getObservationMaskStats()

```ts
getObservationMaskStats(): 
  | {
  activeStamps: number;
  inputsCompacted: number;
  maskedCount: number;
  tokensSaved: number;
}
  | undefined;
```

Defined in: agent.ts:2001

Get observation masking statistics (tokens saved, observations masked, inputs compacted).

#### Returns

  \| \{
  `activeStamps`: `number`;
  `inputsCompacted`: `number`;
  `maskedCount`: `number`;
  `tokensSaved`: `number`;
\}
  \| `undefined`

### getPermission()

```ts
getPermission(toolName): ToolPermission | undefined;
```

Defined in: agent.ts:1798

Get a permission rule by tool name

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `toolName` | `string` |

#### Returns

[`ToolPermission`](Interface.ToolPermission.md) \| `undefined`

### getPermissionLevel()

```ts
getPermissionLevel(toolName): PermissionLevel;
```

Defined in: agent.ts:1824

Get the effective permission level for a tool

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `toolName` | `string` |

#### Returns

[`PermissionLevel`](TypeAlias.PermissionLevel.md)

### getPermissionManager()

```ts
getPermissionManager(): PermissionManager | undefined;
```

Defined in: agent.ts:1861

Get the permission manager (if configured)

#### Returns

[`PermissionManager`](Class.PermissionManager.md) \| `undefined`

### getPermissions()

```ts
getPermissions(): ToolPermission[];
```

Defined in: agent.ts:1805

Get all permission rules

#### Returns

[`ToolPermission`](Interface.ToolPermission.md)[]

### getPin()

```ts
getPin(id): Anchor | undefined;
```

Defined in: agent.ts:1545

Get a pin by ID

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |

#### Returns

[`Anchor`](Interface.Anchor.md) \| `undefined`

### getPinManager()

```ts
getPinManager(): AnchorManager | undefined;
```

Defined in: agent.ts:1591

Get the pin manager (if configured)

#### Returns

[`AnchorManager`](Class.AnchorManager.md) \| `undefined`

### getPins()

```ts
getPins(options?): Anchor[];
```

Defined in: agent.ts:1552

Get all pins, optionally filtered

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `options?` | [`AnchorQueryOptions`](Interface.AnchorQueryOptions.md) |

#### Returns

[`Anchor`](Interface.Anchor.md)[]

### getProjectMemory()

```ts
getProjectMemory(): ProjectMemory | undefined;
```

Defined in: agent.ts:1412

Get the loaded project memory (if any).

Project memory contains instructions loaded from files like
CLAUDE.md, GEMINI.md, PROJECT.md, etc.

#### Returns

[`ProjectMemory`](Interface.ProjectMemory.md) \| `undefined`

The loaded project memory, or undefined if none was loaded

#### Example

```typescript
const memory = agent.getProjectMemory();
if (memory) {
  console.log(`Loaded ${memory.files.length} instruction files`);
  console.log(`Total tokens: ~${memory.estimatedTokens}`);
  for (const file of memory.files) {
    console.log(`  - ${file.relativePath}`);
  }
}
```

### getSessionPermissions()

```ts
getSessionPermissions(): string[];
```

Defined in: agent.ts:1854

Get all tools with session-level permission

#### Returns

`string`[]

### getStreamWriter()

```ts
getStreamWriter(eventName?): StreamWriter;
```

Defined in: agent.ts:1922

Get a stream writer function for emitting custom events.

This returns a simple function that can be passed to tools or
middleware for streaming progress updates.

#### Parameters

| Parameter | Type | Default value | Description |
| ------ | ------ | ------ | ------ |
| `eventName` | `string` | `'stream'` | Name for all events emitted by this writer |

#### Returns

[`StreamWriter`](TypeAlias.StreamWriter.md)

A stream writer function

#### Example

```typescript
const writer = agent.getStreamWriter('myTool');
writer('Starting...', { phase: 'init' });
writer('Processing...', { phase: 'work', progress: 50 });
writer('Done!', { phase: 'complete' });
```

### getSubAgent()

```ts
getSubAgent(name): Agent | undefined;
```

Defined in: agent.ts:2742

Get a registered sub-agent by name

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `name` | `string` |

#### Returns

`Agent` \| `undefined`

### getSubAgentNames()

```ts
getSubAgentNames(): string[];
```

Defined in: agent.ts:2749

Get all registered sub-agent names

#### Returns

`string`[]

### getToolDefinitions()

```ts
getToolDefinitions(): ToolDefinition[];
```

Defined in: agent.ts:2885

Get all registered tool definitions

#### Returns

`ToolDefinition`[]

### getToolRegistry()

```ts
getToolRegistry(): ToolRegistry;
```

Defined in: agent.ts:1987

Get the tool registry instance.
Useful for setting up fallback handlers or inspecting registered tools.

#### Returns

[`ToolRegistry`](Interface.ToolRegistry.md)

### getTotalInputTokens()

```ts
getTotalInputTokens(): number;
```

Defined in: agent.ts:1457

Get total input tokens used across all LLM calls.

#### Returns

`number`

### getTotalOutputTokens()

```ts
getTotalOutputTokens(): number;
```

Defined in: agent.ts:1464

Get total output tokens used across all LLM calls.

#### Returns

`number`

### getTotalTokens()

```ts
getTotalTokens(): number;
```

Defined in: agent.ts:1450

Get total tokens used across all LLM calls.

#### Returns

`number`

### getUsageStats()

```ts
getUsageStats(): UsageStats | undefined;
```

Defined in: agent.ts:1443

Get usage tracking statistics.

#### Returns

[`UsageStats`](Interface.UsageStats.md) \| `undefined`

Usage statistics or undefined if usage tracking is not enabled

#### Example

```typescript
const stats = agent.getUsageStats();
if (stats) {
  console.log(`Total calls: ${stats.totalCalls}`);
  console.log(`Total tokens: ${stats.totalTokens}`);
  console.log(`Input tokens: ${stats.totalInputTokens}`);
  console.log(`Output tokens: ${stats.totalOutputTokens}`);
}
```

### getUsageSummary()

```ts
getUsageSummary(): string | undefined;
```

Defined in: agent.ts:1485

Get a human-readable usage summary.

#### Returns

`string` \| `undefined`

### getVerbosityLevel()

```ts
getVerbosityLevel(): VerbosityLevel;
```

Defined in: agent.ts:2019

Get current verbosity level based on context pressure

#### Returns

[`VerbosityLevel`](TypeAlias.VerbosityLevel.md)

### grantSessionPermission()

```ts
grantSessionPermission(toolName): this;
```

Defined in: agent.ts:1831

Grant session-level permission for a tool

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `toolName` | `string` |

#### Returns

`this`

### ~~hasAnchor()~~

```ts
hasAnchor(id): boolean;
```

Defined in: agent.ts:1661

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |

#### Returns

`boolean`

#### Deprecated

Use hasPin() instead

### ~~hasAnchors()~~

```ts
hasAnchors(): boolean;
```

Defined in: agent.ts:1677

#### Returns

`boolean`

#### Deprecated

Use hasPins() instead

### hasCheckpointer()

```ts
hasCheckpointer(): boolean;
```

Defined in: agent.ts:2348

Check if a checkpointer is configured

#### Returns

`boolean`

### hasGuardrail()

```ts
hasGuardrail(id): boolean;
```

Defined in: agent.ts:1725

Check if a guardrail exists

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |

#### Returns

`boolean`

### hasGuardrails()

```ts
hasGuardrails(): boolean;
```

Defined in: agent.ts:1760

Check if guardrails are enabled

#### Returns

`boolean`

### hasPermissions()

```ts
hasPermissions(): boolean;
```

Defined in: agent.ts:1868

Check if permissions are enabled

#### Returns

`boolean`

### hasPin()

```ts
hasPin(id): boolean;
```

Defined in: agent.ts:1559

Check if a pin exists

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |

#### Returns

`boolean`

### hasPins()

```ts
hasPins(): boolean;
```

Defined in: agent.ts:1598

Check if pins are enabled

#### Returns

`boolean`

### hasProjectMemory()

```ts
hasProjectMemory(): boolean;
```

Defined in: agent.ts:1419

Check if project memory was loaded

#### Returns

`boolean`

### hasUsageTracking()

```ts
hasUsageTracking(): boolean;
```

Defined in: agent.ts:1499

Check if usage tracking is enabled.

#### Returns

`boolean`

### isBudgetExceeded()

```ts
isBudgetExceeded(): boolean;
```

Defined in: agent.ts:1478

Check if budget is exceeded.

#### Returns

`boolean`

### isToolSilent()

```ts
isToolSilent(name): boolean;
```

Defined in: agent.ts:2892

Check if a tool is marked as silent (no spinner or result output)

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `name` | `string` |

#### Returns

`boolean`

### registerTool()

```ts
registerTool(tool): this;
```

Defined in: agent.ts:2864

Register a tool that the agent can call during conversations.

Tools are functions the LLM can invoke to perform actions like reading
files, running commands, or querying APIs. The LLM sees the tool's name,
description, and parameter schema, then decides when to call it.

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `tool` | [`Tool`](Interface.Tool.md) | Tool definition created with `defineTool()` |

#### Returns

`this`

The agent instance (for chaining)

#### Example

```typescript
agent.registerTool(defineTool({
  name: 'get_weather',
  description: 'Get current weather for a city',
  parameters: {
    type: 'object',
    properties: { city: { type: 'string' } },
    required: ['city'],
  },
  execute: async ({ city }) => {
    const data = await fetchWeather(city);
    return { content: JSON.stringify(data) };
  },
}));
```

### registerTools()

```ts
registerTools(tools): this;
```

Defined in: agent.ts:2875

Register multiple tools at once.

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `tools` | [`Tool`](Interface.Tool.md)\<`object`\>[] | Array of tool definitions |

#### Returns

`this`

The agent instance (for chaining)

### ~~removeAnchor()~~

```ts
removeAnchor(id): boolean;
```

Defined in: agent.ts:1665

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |

#### Returns

`boolean`

#### Deprecated

Use removePin() instead

### removeGuardrail()

```ts
removeGuardrail(id): boolean;
```

Defined in: agent.ts:1732

Remove a guardrail by ID

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |

#### Returns

`boolean`

### removePermission()

```ts
removePermission(toolName): boolean;
```

Defined in: agent.ts:1791

Remove a permission rule by tool name

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `toolName` | `string` |

#### Returns

`boolean`

### removePin()

```ts
removePin(id): boolean;
```

Defined in: agent.ts:1568

Remove a pin by ID

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |

#### Returns

`boolean`

true if pin was removed, false if not found

### removeSubAgent()

```ts
removeSubAgent(name): boolean;
```

Defined in: agent.ts:2756

Remove a registered sub-agent (alias for disposeSubAgent)

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `name` | `string` |

#### Returns

`boolean`

### resetUsageTracking()

```ts
resetUsageTracking(): void;
```

Defined in: agent.ts:1492

Reset usage tracking data.

#### Returns

`void`

### resume()

```ts
static resume(sessionId, options): Promise<Agent>;
```

Defined in: agent.ts:2401

Resume an agent from a saved session.

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `sessionId` | `string` | Session ID to resume |
| `options` | \{ `checkpointer`: [`Checkpointer`](Interface.Checkpointer.md); `onEvent?`: [`AgentEventHandler`](TypeAlias.AgentEventHandler.md); `provider`: [`LLMProvider`](Interface.LLMProvider.md); `systemPrompt?`: `string`; `tools?`: [`Tool`](Interface.Tool.md)\<`object`\>[]; \} | Resume options (provider and checkpointer required) |
| `options.checkpointer` | [`Checkpointer`](Interface.Checkpointer.md) | - |
| `options.onEvent?` | [`AgentEventHandler`](TypeAlias.AgentEventHandler.md) | - |
| `options.provider` | [`LLMProvider`](Interface.LLMProvider.md) | - |
| `options.systemPrompt?` | `string` | - |
| `options.tools?` | [`Tool`](Interface.Tool.md)\<`object`\>[] | - |

#### Returns

`Promise`\<`Agent`\>

#### Example

```typescript
const checkpointer = new FileCheckpointer('~/.myapp/sessions/');

// Resume a previous session
const agent = await Agent.resume('session_abc123', {
  provider: new ClaudeProvider({ apiKey: '...' }),
  checkpointer,
});

// Continue the conversation
await agent.run('Continue where we left off...');
```

### revokeSessionPermission()

```ts
revokeSessionPermission(toolName): boolean;
```

Defined in: agent.ts:1839

Revoke session-level permission for a tool

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `toolName` | `string` |

#### Returns

`boolean`

### run()

```ts
run(userMessage, options?): Promise<AgentRunResult>;
```

Defined in: agent.ts:2930

Run the agent with a user message and return the result.

This is the main entry point for agent interaction. The agent will:
1. Add the user message to conversation history
2. Send the conversation to the LLM
3. Execute any tool calls the LLM requests
4. Repeat steps 2-3 until the LLM responds with text (no tool calls)
5. Return the final text response and metadata

Events are emitted throughout the process via the `onEvent` callback
configured at construction time.

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `userMessage` | `string` \| [`ContentBlock`](TypeAlias.ContentBlock.md)[] | The user's message (string or content blocks for images) |
| `options?` | [`RunOptions`](Interface.RunOptions.md) | Optional run configuration (max iterations, abort signal, etc.) |

#### Returns

`Promise`\<[`AgentRunResult`](Interface.AgentRunResult.md)\>

The agent's response, tool call history, and context stats

#### Examples

```typescript
const result = await agent.run('What files are in this directory?');
console.log(result.response);
console.log(`Used ${result.toolCalls.length} tool calls`);
```

```typescript
// With abort signal
const controller = new AbortController();
const result = await agent.run('Refactor this file', {
  signal: controller.signal,
});
```

### runParallelSubAgents()

```ts
runParallelSubAgents(tasks, options?): Promise<SubAgentResult[]>;
```

Defined in: agent.ts:2700

Run multiple sub-agents in parallel with proper state isolation.

This method ensures that parallel sub-agents don't share mutable state,
preventing race conditions and state leakage between concurrent runs.

Inspired by LangGraph issue #6446: Parallel subgraphs with shared
state keys cause InvalidUpdateError.

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `tasks` | \{ `name`: `string`; `task`: `string`; \}[] | Array of {name, task} objects to run in parallel |
| `options?` | [`RunOptions`](Interface.RunOptions.md) | Optional run options applied to all sub-agents |

#### Returns

`Promise`\<[`SubAgentResult`](Interface.SubAgentResult.md)[]\>

Array of results in the same order as tasks

#### Example

```typescript
// Run code review and security scan in parallel
const results = await agent.runParallelSubAgents([
  { name: 'code-reviewer', task: 'Review src/auth.ts' },
  { name: 'security-scanner', task: 'Scan src/auth.ts for vulnerabilities' },
]);
```

### runSubAgent()

```ts
runSubAgent(
   name, 
   task, 
options?): Promise<SubAgentResult>;
```

Defined in: agent.ts:2589

Run a sub-agent with a specific task.

The sub-agent executes independently with its own context and returns
the result to the parent agent.

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `name` | `string` | Name of the registered sub-agent |
| `task` | `string` | Task description for the sub-agent |
| `options?` | [`RunOptions`](Interface.RunOptions.md) | Optional run options |

#### Returns

`Promise`\<[`SubAgentResult`](Interface.SubAgentResult.md)\>

### serialize()

```ts
serialize(): AgentState;
```

Defined in: agent.ts:2301

Serialize the current agent state to an AgentState object.
This can be used for manual persistence or transferring state.

#### Returns

[`AgentState`](Interface.AgentState.md)

#### Example

```typescript
const state = agent.serialize();
const json = JSON.stringify(state);
// Store json somewhere...
```

### setHistory()

```ts
setHistory(messages, options?): Promise<Agent>;
```

Defined in: agent.ts:1954

Set the conversation history (for manual compaction/restoration)
Also updates the context manager's token count if configured.

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `messages` | [`Message`](Interface.Message.md)[] | The message history to restore |
| `options?` | \{ `turnCount?`: `number`; \} | Optional restore options |
| `options.turnCount?` | `number` | The turn count to restore (important for compaction) |

#### Returns

`Promise`\<`Agent`\>

### setModel()

```ts
setModel(modelId): void;
```

Defined in: agent.ts:1637

Change the model for subsequent LLM calls (same provider only).

Takes effect on the next `run()` or `stream()` call — never interrupts
a running turn. Conversation history is preserved (it's provider-agnostic).
Emits a `model_changed` event.

Use this to switch between models within the same provider, e.g.,
Claude Sonnet → Claude Opus for a harder task, then back.

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `modelId` | `string` | The new model ID (e.g., 'claude-opus-4-20250514') |

#### Returns

`void`

#### Throws

If modelId is empty or not a string

#### Example

```typescript
console.log(agent.getModel()); // 'claude-sonnet-4-20250514'
agent.setModel('claude-opus-4-20250514');
// Next run() uses Opus
const result = await agent.run('Solve this complex problem');
agent.setModel('claude-sonnet-4-20250514'); // Switch back
```

#### Since

0.5.8

### setPermissionLevel()

```ts
setPermissionLevel(
   toolName, 
   level, 
   description?): this;
```

Defined in: agent.ts:1816

Set the permission level for a tool

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `toolName` | `string` | Tool name or pattern |
| `level` | [`PermissionLevel`](TypeAlias.PermissionLevel.md) | Permission level |
| `description?` | `string` | Optional description |

#### Returns

`this`

### stream()

```ts
stream(userMessage, options?): AsyncIterable<AgentEvent>;
```

Defined in: agent.ts:4112

Stream the agent's response as events.

Yields `AgentEvent` objects in real time as the agent thinks, calls tools,
and generates text. Use this for building interactive UIs that show
progress as it happens.

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `userMessage` | `string` | The user's message |
| `options?` | [`RunOptions`](Interface.RunOptions.md) | Optional run configuration |

#### Returns

`AsyncIterable`\<[`AgentEvent`](TypeAlias.AgentEvent.md)\>

An async iterable of agent events

#### Example

```typescript
for await (const event of agent.stream('Explain this code')) {
  if (event.type === 'llm_chunk') {
    process.stdout.write(event.chunk.text ?? '');
  } else if (event.type === 'tool_start') {
    console.log(`\nCalling tool: ${event.name}`);
  } else if (event.type === 'done') {
    console.log('\n\nDone!');
  }
}
```
