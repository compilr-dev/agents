---
title: "StateError"
parent: Classes
nav_order: 1
---


# Class: StateError

Defined in: state/errors.ts:36

Base error class for state management operations.

## Extends

- `Error`

## Constructors

### Constructor

```ts
new StateError(
   message, 
   code, 
   cause?): StateError;
```

Defined in: state/errors.ts:47

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `message` | `string` |
| `code` | [`StateErrorCode`](Enumeration.StateErrorCode.md) |
| `cause?` | `Error` |

#### Returns

`StateError`

#### Overrides

```ts
Error.constructor
```

## Properties

### cause?

```ts
readonly optional cause?: Error;
```

Defined in: state/errors.ts:45

Original error that caused this error (if any)

#### Overrides

```ts
Error.cause
```

### code

```ts
readonly code: StateErrorCode;
```

Defined in: state/errors.ts:40

Error code for programmatic handling

## Methods

### deserialization()

```ts
static deserialization(message, cause?): StateError;
```

Defined in: state/errors.ts:71

Create a deserialization error

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `message` | `string` |
| `cause?` | `Error` |

#### Returns

`StateError`

### invalidSessionId()

```ts
static invalidSessionId(sessionId): StateError;
```

Defined in: state/errors.ts:113

Create an invalid session ID error

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `sessionId` | `string` |

#### Returns

`StateError`

### invalidState()

```ts
static invalidState(message): StateError;
```

Defined in: state/errors.ts:106

Create an invalid state error

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `message` | `string` |

#### Returns

`StateError`

### serialization()

```ts
static serialization(message, cause?): StateError;
```

Defined in: state/errors.ts:60

Create a serialization error

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `message` | `string` |
| `cause?` | `Error` |

#### Returns

`StateError`

### sessionNotFound()

```ts
static sessionNotFound(sessionId): StateError;
```

Defined in: state/errors.ts:82

Create a session not found error

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `sessionId` | `string` |

#### Returns

`StateError`

### storage()

```ts
static storage(message, cause?): StateError;
```

Defined in: state/errors.ts:89

Create a storage error

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `message` | `string` |
| `cause?` | `Error` |

#### Returns

`StateError`

### versionMismatch()

```ts
static versionMismatch(expected, actual): StateError;
```

Defined in: state/errors.ts:96

Create a version mismatch error

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `expected` | `number` |
| `actual` | `number` |

#### Returns

`StateError`
