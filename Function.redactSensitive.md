---
title: "redactSensitive"
parent: Functions
nav_order: 1
---


# Function: redactSensitive()

```ts
function redactSensitive(data, sensitiveKeys?): Record<string, unknown>;
```

Defined in: tracing/logging.ts:286

Redact sensitive data from an object

## Parameters

| Parameter | Type |
| ------ | ------ |
| `data` | `Record`\<`string`, `unknown`\> |
| `sensitiveKeys` | `string`[] |

## Returns

`Record`\<`string`, `unknown`\>
