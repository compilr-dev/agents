---
title: "ContextManagerOptions"
parent: Interfaces
nav_order: 1
---


# Interface: ContextManagerOptions

Defined in: context/manager.ts:94

Options for creating a ContextManager

## Properties

### config?

```ts
optional config?: Partial<ContextConfig>;
```

Defined in: context/manager.ts:103

Configuration overrides

### fileTracker?

```ts
optional fileTracker?: FileAccessTracker;
```

Defined in: context/manager.ts:115

File access tracker for context restoration hints.
When provided, compaction/summarization will inject hints
about previously accessed files.

### onEvent?

```ts
optional onEvent?: ContextEventHandler;
```

Defined in: context/manager.ts:108

Event handler for context events

### provider

```ts
provider: LLMProvider;
```

Defined in: context/manager.ts:98

LLM provider (for token counting)
