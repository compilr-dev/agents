---
title: "ContextConfigInput"
parent: Interfaces
nav_order: 1
---


# Interface: ContextConfigInput

Defined in: context/manager.ts:104

What a caller may pass as `config`.

⚠️ NOT `Partial<ContextConfig>`. `Partial` is SHALLOW, so that type demanded a complete
`FilteringConfig` the moment you set one field of it — while `mergeConfig` spreads each
section over its default (`{ ...DEFAULT.filtering, ...partial.filtering }`), which means a
NESTED partial is precisely the supported input. The test named "should merge partial config
with defaults" could not typecheck against the type of the thing it tests, and nor could any
caller that wanted to change one knob.

## Properties

### budget?

```ts
optional budget?: Partial<BudgetAllocation>;
```

Defined in: context/manager.ts:106

### compaction?

```ts
optional compaction?: Partial<CompactionConfig>;
```

Defined in: context/manager.ts:109

### filtering?

```ts
optional filtering?: Partial<FilteringConfig>;
```

Defined in: context/manager.ts:108

### maxContextTokens?

```ts
optional maxContextTokens?: number;
```

Defined in: context/manager.ts:105

### summarization?

```ts
optional summarization?: Partial<SummarizationConfig>;
```

Defined in: context/manager.ts:110

### verbosity?

```ts
optional verbosity?: Partial<VerbosityConfig>;
```

Defined in: context/manager.ts:107
