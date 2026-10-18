---
title: "PendingWrite"
parent: Interfaces
nav_order: 1
---


# Interface: PendingWrite

Defined in: state/types.ts:287

Pending write from incomplete tool execution.
Used for fault-tolerant checkpointing.

## Properties

### completedAt

```ts
completedAt: string;
```

Defined in: state/types.ts:310

When the write was completed (ISO 8601)

### result

```ts
result: {
  error?: string;
  result?: unknown;
  success: boolean;
};
```

Defined in: state/types.ts:301

Tool execution result

#### error?

```ts
optional error?: string;
```

#### result?

```ts
optional result?: unknown;
```

#### success

```ts
success: boolean;
```

### toolCallId

```ts
toolCallId: string;
```

Defined in: state/types.ts:291

Tool call ID

### toolName

```ts
toolName: string;
```

Defined in: state/types.ts:296

Tool name
