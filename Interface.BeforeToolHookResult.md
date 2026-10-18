---
title: "BeforeToolHookResult"
parent: Interfaces
nav_order: 1
---


# Interface: BeforeToolHookResult

Defined in: hooks/types.ts:231

Result from before:tool hook that can skip or modify execution

## Properties

### input?

```ts
optional input?: Record<string, unknown>;
```

Defined in: hooks/types.ts:245

Modified input (when not skipping)

### result?

```ts
optional result?: ToolExecutionResult;
```

Defined in: hooks/types.ts:240

Custom result to return (when skip is true)

### skip?

```ts
optional skip?: boolean;
```

Defined in: hooks/types.ts:235

Skip tool execution and use this result instead
