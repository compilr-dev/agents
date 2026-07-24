---
title: "retry"
parent: Functions
nav_order: 1
---


# ~~Function: retry()~~

```ts
function retry<T>(fn, options?): Promise<T>;
```

Defined in: utils/index.ts:307

## Type Parameters

| Type Parameter |
| ------ |
| `T` |

## Parameters

| Parameter | Type |
| ------ | ------ |
| `fn` | () => `Promise`\<`T`\> |
| `options` | \{ `baseDelay?`: `number`; `maxDelay?`: `number`; `maxRetries?`: `number`; \} |
| `options.baseDelay?` | `number` |
| `options.maxDelay?` | `number` |
| `options.maxRetries?` | `number` |

## Returns

`Promise`\<`T`\>

## Deprecated

Use withRetry instead. This function is kept for backward compatibility.
