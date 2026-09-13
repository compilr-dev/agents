---
title: "StructuredLogger"
parent: Interfaces
nav_order: 1
---


# Interface: StructuredLogger

Defined in: tracing/types.ts:302

Logger interface for structured logging

## Methods

### child()

```ts
child(context): StructuredLogger;
```

Defined in: tracing/types.ts:308

Create a child logger with additional context

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `context` | `Record`\<`string`, `unknown`\> |

#### Returns

`StructuredLogger`

### debug()

```ts
debug(message, data?): void;
```

Defined in: tracing/types.ts:303

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `message` | `string` |
| `data?` | `Record`\<`string`, `unknown`\> |

#### Returns

`void`

### error()

```ts
error(
   message, 
   error?, 
   data?): void;
```

Defined in: tracing/types.ts:306

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `message` | `string` |
| `error?` | `Error` |
| `data?` | `Record`\<`string`, `unknown`\> |

#### Returns

`void`

### info()

```ts
info(message, data?): void;
```

Defined in: tracing/types.ts:304

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `message` | `string` |
| `data?` | `Record`\<`string`, `unknown`\> |

#### Returns

`void`

### setCorrelation()

```ts
setCorrelation(
   traceId?, 
   spanId?, 
   sessionId?): void;
```

Defined in: tracing/types.ts:310

Set correlation IDs

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `traceId?` | `string` |
| `spanId?` | `string` |
| `sessionId?` | `string` |

#### Returns

`void`

### warn()

```ts
warn(message, data?): void;
```

Defined in: tracing/types.ts:305

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `message` | `string` |
| `data?` | `Record`\<`string`, `unknown`\> |

#### Returns

`void`
