---
title: "InjectionMatch"
parent: Interfaces
nav_order: 1
---


# Interface: InjectionMatch

Defined in: guardrails/injection-detection.ts:178

A single injection match

## Properties

### category

```ts
category: string;
```

Defined in: guardrails/injection-detection.ts:182

### description

```ts
description: string;
```

Defined in: guardrails/injection-detection.ts:180

### matchedText

```ts
matchedText: string;
```

Defined in: guardrails/injection-detection.ts:184

The text that matched

### patternId

```ts
patternId: string;
```

Defined in: guardrails/injection-detection.ts:179

### severity

```ts
severity: "low" | "medium" | "high";
```

Defined in: guardrails/injection-detection.ts:181

### source?

```ts
optional source?: string;
```

Defined in: guardrails/injection-detection.ts:186

Where the content came from (if known)
