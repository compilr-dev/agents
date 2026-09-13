---
title: "ErrorHookResult"
parent: Interfaces
nav_order: 1
---


# Interface: ErrorHookResult

Defined in: hooks/types.ts:328

Result from error hook that can recover or transform the error

## Properties

### error?

```ts
optional error?: Error;
```

Defined in: hooks/types.ts:337

Transformed error to throw instead

### handled?

```ts
optional handled?: boolean;
```

Defined in: hooks/types.ts:332

Whether to suppress the error and continue

### recovery?

```ts
optional recovery?: ToolExecutionResult;
```

Defined in: hooks/types.ts:342

Recovery result (for tool errors, replaces failed result)
