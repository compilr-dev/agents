---
title: "detectInjection"
parent: Functions
nav_order: 1
---


# Function: detectInjection()

```ts
function detectInjection(
   content, 
   source?, 
   patterns?): InjectionDetectionResult;
```

Defined in: guardrails/injection-detection.ts:199

Scan text content for prompt injection patterns.

## Parameters

| Parameter | Type | Default value | Description |
| ------ | ------ | ------ | ------ |
| `content` | `string` | `undefined` | Text to scan |
| `source?` | `string` | `undefined` | Optional label for where the content came from (e.g., "file: README.md") |
| `patterns?` | [`InjectionPattern`](Interface.InjectionPattern.md)[] | `INJECTION_PATTERNS` | Optional custom patterns (defaults to INJECTION_PATTERNS) |

## Returns

[`InjectionDetectionResult`](Interface.InjectionDetectionResult.md)

Detection result with all matches
