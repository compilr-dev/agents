---
title: "InjectionHookOptions"
parent: Interfaces
nav_order: 1
---


# Interface: InjectionHookOptions

Defined in: guardrails/injection-hook.ts:33

## Properties

### additionalTools?

```ts
optional additionalTools?: string[];
```

Defined in: guardrails/injection-hook.ts:37

Additional tool names to scan

### minSeverity?

```ts
optional minSeverity?: "low" | "medium" | "high";
```

Defined in: guardrails/injection-hook.ts:35

Minimum severity to trigger a warning (default: 'medium')

### onDetected?

```ts
optional onDetected?: (result, toolName) => void;
```

Defined in: guardrails/injection-hook.ts:39

Called when injection is detected (for logging/telemetry)

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `result` | [`InjectionDetectionResult`](Interface.InjectionDetectionResult.md) |
| `toolName` | `string` |

#### Returns

`void`
