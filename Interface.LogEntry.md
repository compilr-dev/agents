---
title: "LogEntry"
parent: Interfaces
nav_order: 1
---


# Interface: LogEntry

Defined in: tracing/types.ts:276

Structured log entry

## Properties

### data?

```ts
optional data?: Record<string, unknown>;
```

Defined in: tracing/types.ts:290

Additional structured data

### error?

```ts
optional error?: {
  message: string;
  name: string;
  stack?: string;
};
```

Defined in: tracing/types.ts:292

Error information

#### message

```ts
message: string;
```

#### name

```ts
name: string;
```

#### stack?

```ts
optional stack?: string;
```

### level

```ts
level: LogLevel;
```

Defined in: tracing/types.ts:278

Log level

### message

```ts
message: string;
```

Defined in: tracing/types.ts:280

Log message

### sessionId?

```ts
optional sessionId?: string;
```

Defined in: tracing/types.ts:288

Session ID

### spanId?

```ts
optional spanId?: string;
```

Defined in: tracing/types.ts:286

Span ID for correlation

### timestamp

```ts
timestamp: string;
```

Defined in: tracing/types.ts:282

Timestamp in ISO format

### traceId?

```ts
optional traceId?: string;
```

Defined in: tracing/types.ts:284

Trace ID for correlation
