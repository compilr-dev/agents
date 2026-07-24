---
title: "HooksConfig"
parent: Interfaces
nav_order: 1
---


# Interface: HooksConfig

Defined in: hooks/types.ts:365

Configuration for the hooks system

## Properties

### afterIteration?

```ts
optional afterIteration?: AfterIterationHook[];
```

Defined in: hooks/types.ts:374

Hooks called after each iteration

### afterLLM?

```ts
optional afterLLM?: AfterLLMHook[];
```

Defined in: hooks/types.ts:384

Hooks called after LLM responses

### afterTool?

```ts
optional afterTool?: AfterToolHook[];
```

Defined in: hooks/types.ts:394

Hooks called after tool execution

### beforeIteration?

```ts
optional beforeIteration?: BeforeIterationHook[];
```

Defined in: hooks/types.ts:369

Hooks called before each iteration

### beforeLLM?

```ts
optional beforeLLM?: BeforeLLMHook[];
```

Defined in: hooks/types.ts:379

Hooks called before LLM calls

### beforeTool?

```ts
optional beforeTool?: BeforeToolHook[];
```

Defined in: hooks/types.ts:389

Hooks called before tool execution

### onError?

```ts
optional onError?: OnErrorHook[];
```

Defined in: hooks/types.ts:399

Hooks called when errors occur
