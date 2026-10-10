---
title: "createTracingHooks"
parent: Functions
nav_order: 1
---


# Function: createTracingHooks()

```ts
function createTracingHooks(manager, config?): HooksConfig;
```

Defined in: tracing/hooks.ts:62

Create tracing hooks that automatically instrument agent execution

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `manager` | [`TracingManager`](Class.TracingManager.md) | TracingManager instance |
| `config` | [`TracingHooksConfig`](Interface.TracingHooksConfig.md) | Tracing hooks configuration |

## Returns

[`HooksConfig`](Interface.HooksConfig.md)

HooksConfig with tracing hooks

## Example

```typescript
const tracingManager = new TracingManager({ serviceName: 'my-agent' });
const tracingHooks = createTracingHooks(tracingManager, {
  traceLLM: true,
  traceTools: true,
  traceIterations: true,
});

const agent = new Agent({
  provider,
  hooks: tracingHooks,
});
```
