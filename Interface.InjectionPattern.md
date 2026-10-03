---
title: "InjectionPattern"
parent: Interfaces
nav_order: 1
---


# Interface: InjectionPattern

Defined in: guardrails/injection-detection.ts:19

Prompt Injection Detection — Scans input content for manipulation attempts.

Detects patterns in user messages, file contents, web fetches, and knowledge
base documents that try to override the agent's instructions.

Two attack categories:
  - Direct: user explicitly tries to override ("ignore previous instructions")
  - Indirect: embedded in external content (files, web pages) that the agent reads

Detection is pattern-based (fast, no LLM call). Not exhaustive, but catches
the obvious attacks with low false-positive rates.

## Properties

### category

```ts
category: 
  | "instruction-override"
  | "role-hijack"
  | "system-prompt-leak"
  | "data-exfiltration";
```

Defined in: guardrails/injection-detection.ts:29

Category of attack

### description

```ts
description: string;
```

Defined in: guardrails/injection-detection.ts:23

Human-readable description

### id

```ts
id: string;
```

Defined in: guardrails/injection-detection.ts:21

Unique identifier

### pattern

```ts
pattern: RegExp;
```

Defined in: guardrails/injection-detection.ts:25

Regex pattern (case-insensitive)

### severity

```ts
severity: "low" | "medium" | "high";
```

Defined in: guardrails/injection-detection.ts:27

Severity: low (suspicious), medium (likely), high (definite)
