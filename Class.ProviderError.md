---
title: "ProviderError"
parent: Classes
nav_order: 1
---


# Class: ProviderError

Defined in: errors.ts:41

Error thrown when an LLM provider API call fails.

## Example

```typescript
throw new ProviderError(
  'Rate limit exceeded. Retry after 60s',
  'claude',
  429
);
```

## Extends

- [`AgentError`](Class.AgentError.md)

## Constructors

### Constructor

```ts
new ProviderError(
   message, 
   provider, 
   statusCode?, 
   cause?): ProviderError;
```

Defined in: errors.ts:42

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `message` | `string` |
| `provider` | `string` |
| `statusCode?` | `number` |
| `cause?` | `Error` |

#### Returns

`ProviderError`

#### Overrides

[`AgentError`](Class.AgentError.md).[`constructor`](Class.AgentError.md#constructor)

## Properties

### cause?

```ts
readonly optional cause?: Error;
```

Defined in: errors.ts:17

#### Inherited from

[`AgentError`](Class.AgentError.md).[`cause`](Class.AgentError.md#cause)

### provider

```ts
readonly provider: string;
```

Defined in: errors.ts:44

### statusCode?

```ts
readonly optional statusCode?: number;
```

Defined in: errors.ts:45

## Methods

### isAuthError()

```ts
isAuthError(): boolean;
```

Defined in: errors.ts:62

Check if this is an authentication error (HTTP 401/403)

#### Returns

`boolean`

### isConnectionError()

```ts
isConnectionError(): boolean;
```

Defined in: errors.ts:77

Check if this is a connection/network error.
These errors typically have no status code but are retryable.

#### Returns

`boolean`

### isOverloadedError()

```ts
isOverloadedError(): boolean;
```

Defined in: errors.ts:97

Check if this is an Anthropic overloaded error (529)

#### Returns

`boolean`

### isRateLimitError()

```ts
isRateLimitError(): boolean;
```

Defined in: errors.ts:55

Check if this is a rate limit error (HTTP 429)

#### Returns

`boolean`

### isRetryable()

```ts
isRetryable(): boolean;
```

Defined in: errors.ts:114

Check if this error is retryable.
Retryable errors include:
- Rate limit (429)
- Server errors (5xx)
- Connection/network errors
- Anthropic overloaded (529)

Non-retryable errors include:
- Authentication errors (401, 403)
- Bad request (400)
- Not found (404)

#### Returns

`boolean`

### isServerError()

```ts
isServerError(): boolean;
```

Defined in: errors.ts:69

Check if this is a server error (HTTP 5xx)

#### Returns

`boolean`
