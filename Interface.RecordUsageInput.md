---
title: "RecordUsageInput"
parent: Interfaces
nav_order: 1
---


# Interface: RecordUsageInput

Defined in: costs/types.ts:153

Input for recording usage

## Properties

### metadata?

```ts
optional metadata?: Record<string, unknown>;
```

Defined in: costs/types.ts:163

Additional metadata

### model

```ts
model: string;
```

Defined in: costs/types.ts:155

Model used

### provider

```ts
provider: string;
```

Defined in: costs/types.ts:157

Provider name

### sessionId?

```ts
optional sessionId?: string;
```

Defined in: costs/types.ts:161

Session ID override

### tokens

```ts
tokens: TokenUsage;
```

Defined in: costs/types.ts:159

Token usage
