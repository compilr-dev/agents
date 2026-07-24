---
title: "TaskToolOptions"
parent: Interfaces
nav_order: 1
---


# Interface: TaskToolOptions

Defined in: tools/builtin/task.ts:189

Options for creating a task tool

## Properties

### agentTypes

```ts
agentTypes: Record<string, AgentTypeConfig>;
```

Defined in: tools/builtin/task.ts:198

Available agent types and their configurations

### defaultTimeout?

```ts
optional defaultTimeout?: number;
```

Defined in: tools/builtin/task.ts:214

Default timeout for sub-agent execution in ms (default: 300000 = 5 min)

### enableEventStreaming?

```ts
optional enableEventStreaming?: boolean;
```

Defined in: tools/builtin/task.ts:242

Enable event streaming from sub-agents (default: false)
When enabled, sub-agent events are forwarded to onSubAgentEvent

### maxConcurrent?

```ts
optional maxConcurrent?: number;
```

Defined in: tools/builtin/task.ts:209

Maximum concurrent sub-agents (default: 3)

### onComplete?

```ts
optional onComplete?: (agentType, result, toolUseId?) => void;
```

Defined in: tools/builtin/task.ts:230

Called when a sub-agent completes.

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `agentType` | `string` | The type of agent that completed |
| `result` | [`TaskResult`](Interface.TaskResult.md) | The task result |
| `toolUseId?` | `string` | Tool use ID for correlation (enables parallel tracking) |

#### Returns

`void`

### onSpawn?

```ts
optional onSpawn?: (agentType, description, toolUseId?) => void;
```

Defined in: tools/builtin/task.ts:222

Called when a sub-agent is spawned.

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `agentType` | `string` | The type of agent being spawned |
| `description` | `string` | Description of the task |
| `toolUseId?` | `string` | Tool use ID for correlation (enables parallel tracking) |

#### Returns

`void`

### onSubAgentEvent?

```ts
optional onSubAgentEvent?: (eventInfo) => void;
```

Defined in: tools/builtin/task.ts:236

Called when a sub-agent emits an event (for real-time streaming)
Only called if enableEventStreaming is true

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `eventInfo` | [`SubAgentEventInfo`](Interface.SubAgentEventInfo.md) |

#### Returns

`void`

### parentAgent

```ts
parentAgent: Agent;
```

Defined in: tools/builtin/task.ts:193

The parent agent that will spawn sub-agents

### providerFactory?

```ts
optional providerFactory?: (model) => LLMProvider;
```

Defined in: tools/builtin/task.ts:204

Provider factory for creating sub-agent providers
Called with model name, returns LLM provider

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `model` | `string` |

#### Returns

[`LLMProvider`](Interface.LLMProvider.md)
