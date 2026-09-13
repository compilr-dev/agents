---
title: "mergeHooks"
parent: Functions
nav_order: 1
---


# Function: mergeHooks()

```ts
function mergeHooks(...configs): HooksConfig;
```

Defined in: tracing/hooks.ts:430

Merge multiple HooksConfig objects

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| ...`configs` | [`HooksConfig`](Interface.HooksConfig.md)[] | HooksConfig objects to merge |

## Returns

[`HooksConfig`](Interface.HooksConfig.md)

Merged HooksConfig

## Example

```typescript
const hooks = mergeHooks(tracingHooks, loggingHooks, customHooks);
const agent = new Agent({ provider, hooks });
```
