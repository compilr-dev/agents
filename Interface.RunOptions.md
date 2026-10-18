---
title: "RunOptions"
parent: Interfaces
nav_order: 1
---


# Interface: RunOptions

Defined in: agent.ts:737

Options for a single run

## Properties

### chatOptions?

```ts
optional chatOptions?: ChatOptions;
```

Defined in: agent.ts:751

Override chat options for this run

### getToolContext?

```ts
optional getToolContext?: (toolName, toolUseId) => Partial<Omit<ToolExecutionContext, "toolUseId" | "onOutput">>;
```

Defined in: agent.ts:796

Callback to provide additional tool execution context.
Called before each tool execution, allowing the caller to inject
abort signals or other context-specific options.

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `toolName` | `string` |
| `toolUseId` | `string` |

#### Returns

`Partial`\<`Omit`\<`ToolExecutionContext`, `"toolUseId"` \| `"onOutput"`\>\>

#### Example

```typescript
// Provide abort signal for bash commands (for Ctrl+B backgrounding)
const bashAbortController = new AbortController();
await agent.stream(message, {
  getToolContext: (toolName, toolUseId) => {
    if (toolName === 'bash') {
      return {
        abortSignal: bashAbortController.signal,
        onBackground: (shellId, output) => { ... },
      };
    }
    return {};
  },
});
```

### maxIterations?

```ts
optional maxIterations?: number;
```

Defined in: agent.ts:746

Override max iterations for this run

### onEvent?

```ts
optional onEvent?: AgentEventHandler;
```

Defined in: agent.ts:756

Event handler for this run (in addition to config handler)

### signal?

```ts
optional signal?: AbortSignal;
```

Defined in: agent.ts:741

AbortSignal for cancellation

### toolFilter?

```ts
optional toolFilter?: string[];
```

Defined in: agent.ts:772

Filter tools for this run.
- If provided, only these tool names will be available
- Reduces token usage by not sending unused tool definitions
- Tools must be registered with the agent

#### Example

```typescript
// Only allow file and search tools for this request
await agent.run(message, {
  toolFilter: ['read_file', 'write_file', 'grep', 'glob'],
});
```
