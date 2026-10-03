---
title: "UsageRecord"
parent: Interfaces
nav_order: 1
---


# Interface: UsageRecord

Defined in: costs/types.ts:28

A single usage record

## Properties

### id

```ts
id: string;
```

Defined in: costs/types.ts:30

Unique ID for this record

### metadata?

```ts
optional metadata?: Record<string, unknown>;
```

Defined in: costs/types.ts:42

Additional metadata

### model

```ts
model: string;
```

Defined in: costs/types.ts:34

Model used

### provider

```ts
provider: string;
```

Defined in: costs/types.ts:36

Provider name

### sessionId?

```ts
optional sessionId?: string;
```

Defined in: costs/types.ts:40

Session ID (if tracking by session)

### timestamp

```ts
timestamp: Date;
```

Defined in: costs/types.ts:32

Timestamp of the call

### tokens

```ts
tokens: TokenUsage;
```

Defined in: costs/types.ts:38

Token usage
