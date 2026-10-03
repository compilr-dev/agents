---
title: "ParsedOpenAIModel"
parent: Interfaces
nav_order: 1
---


# Interface: ParsedOpenAIModel

Defined in: providers/openai-models.ts:26

A parsed OpenAI model id. `minor` is 0 when the id carries no `.n` part.

## Properties

### major

```ts
major: number;
```

Defined in: providers/openai-models.ts:27

### minor

```ts
minor: number;
```

Defined in: providers/openai-models.ts:28

### variant?

```ts
optional variant?: string;
```

Defined in: providers/openai-models.ts:30

The named tier of a generation: `astra`, `sol`, `luna`, `terra`, `mini`, `nano`, …
