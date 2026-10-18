---
title: "StructuredLoggerOptions"
parent: Interfaces
nav_order: 1
---


# Interface: StructuredLoggerOptions

Defined in: tracing/types.ts:316

Options for creating a structured logger

## Properties

### context?

```ts
optional context?: Record<string, unknown>;
```

Defined in: tracing/types.ts:326

Initial context

### level?

```ts
optional level?: LogLevel;
```

Defined in: tracing/types.ts:318

Minimum log level

### output?

```ts
optional output?: (entry) => void;
```

Defined in: tracing/types.ts:324

Output function (default: console.log)

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `entry` | [`LogEntry`](Interface.LogEntry.md) |

#### Returns

`void`

### prettyPrint?

```ts
optional prettyPrint?: boolean;
```

Defined in: tracing/types.ts:322

Pretty print JSON (default: false for production)

### serviceName?

```ts
optional serviceName?: string;
```

Defined in: tracing/types.ts:320

Service name
