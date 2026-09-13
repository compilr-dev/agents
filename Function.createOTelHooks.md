---
title: "createOTelHooks"
parent: Functions
nav_order: 1
---


# Function: createOTelHooks()

```ts
function createOTelHooks(config?): HooksConfig;
```

Defined in: tracing/otel-hooks.ts:95

Create native OpenTelemetry hooks for agent instrumentation.

These hooks create real OTel spans during execution, as opposed to the
post-hoc `createOTelExporter()` which recreates spans after the fact.

Span hierarchy:
```
agent.iteration [INTERNAL]
  ├── gen_ai.chat [CLIENT]           (gen_ai.system, tokens, model)
  ├── agent.tool.read_file [INTERNAL] (tool.name, success, duration)
  └── agent.tool.bash [INTERNAL]
```

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `config` | [`OTelHooksConfig`](Interface.OTelHooksConfig.md) | Optional configuration |

## Returns

[`HooksConfig`](Interface.HooksConfig.md)

HooksConfig ready to pass to Agent constructor
