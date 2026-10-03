---
title: "InjectionDetectionResult"
parent: Interfaces
nav_order: 1
---


# Interface: InjectionDetectionResult

Defined in: guardrails/injection-detection.ts:166

Result of scanning content for injection

## Properties

### detected

```ts
detected: boolean;
```

Defined in: guardrails/injection-detection.ts:168

Whether any injection was detected

### matches

```ts
matches: InjectionMatch[];
```

Defined in: guardrails/injection-detection.ts:170

All matches found

### maxSeverity

```ts
maxSeverity: "low" | "medium" | "high" | "none";
```

Defined in: guardrails/injection-detection.ts:172

Highest severity found

### summary

```ts
summary: string;
```

Defined in: guardrails/injection-detection.ts:174

Summary message for the user/agent
