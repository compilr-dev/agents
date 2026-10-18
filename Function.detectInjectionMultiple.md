---
title: "detectInjectionMultiple"
parent: Functions
nav_order: 1
---


# Function: detectInjectionMultiple()

```ts
function detectInjectionMultiple(sources): InjectionDetectionResult;
```

Defined in: guardrails/injection-detection.ts:244

Scan multiple content sources and aggregate results.

## Parameters

| Parameter | Type |
| ------ | ------ |
| `sources` | \{ `content`: `string`; `label`: `string`; \}[] |

## Returns

[`InjectionDetectionResult`](Interface.InjectionDetectionResult.md)
