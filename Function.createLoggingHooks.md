---
title: "createLoggingHooks"
parent: Functions
nav_order: 1
---


# Function: createLoggingHooks()

```ts
function createLoggingHooks(logger?): HooksConfig;
```

Defined in: tracing/hooks.ts:332

Create a simple logging hook that logs all agent events

## Parameters

| Parameter | Type | Default value | Description |
| ------ | ------ | ------ | ------ |
| `logger` | (`message`, `data?`) => `void` | `console.log` | Logger function (default: console.log) |

## Returns

[`HooksConfig`](Interface.HooksConfig.md)

HooksConfig with logging hooks

## Example

```typescript
const loggingHooks = createLoggingHooks((msg) => myLogger.info(msg));
const agent = new Agent({ provider, hooks: loggingHooks });
```
