---
title: "MockResponse"
parent: Interfaces
nav_order: 1
---


# Interface: MockResponse

Defined in: providers/mock.ts:54

A mock response definition

## Properties

### delay?

```ts
optional delay?: number;
```

Defined in: providers/mock.ts:64

Delay in ms before responding (simulates network latency)

### error?

```ts
optional error?: Error;
```

Defined in: providers/mock.ts:62

If set, throw this error instead of responding

### text?

```ts
optional text?: string;
```

Defined in: providers/mock.ts:56

Text content of the response

### thinking?

```ts
optional thinking?: MockThinking;
```

Defined in: providers/mock.ts:60

Extended thinking content (Claude-specific)

### toolCalls?

```ts
optional toolCalls?: MockToolCall[];
```

Defined in: providers/mock.ts:58

Tool calls to include in the response
