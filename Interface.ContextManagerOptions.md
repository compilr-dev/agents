---
title: "ContextManagerOptions"
parent: Interfaces
nav_order: 1
---


# Interface: ContextManagerOptions

Defined in: context/manager.ts:113

## Properties

### config?

```ts
optional config?: ContextConfigInput;
```

Defined in: context/manager.ts:122

Configuration overrides

### fileTracker?

```ts
optional fileTracker?: FileAccessTracker;
```

Defined in: context/manager.ts:134

File access tracker for context restoration hints.
When provided, compaction/summarization will inject hints
about previously accessed files.

### onEvent?

```ts
optional onEvent?: ContextEventHandler;
```

Defined in: context/manager.ts:127

Event handler for context events

### provider

```ts
provider: LLMProvider;
```

Defined in: context/manager.ts:117

LLM provider (for token counting)
