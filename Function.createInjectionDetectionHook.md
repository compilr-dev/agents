---
title: "createInjectionDetectionHook"
parent: Functions
nav_order: 1
---


# Function: createInjectionDetectionHook()

```ts
function createInjectionDetectionHook(options?): AfterToolHook;
```

Defined in: guardrails/injection-hook.ts:88

Create an afterTool hook that scans content-reading tool results for prompt injection.

## Parameters

| Parameter | Type |
| ------ | ------ |
| `options?` | [`InjectionHookOptions`](Interface.InjectionHookOptions.md) |

## Returns

[`AfterToolHook`](TypeAlias.AfterToolHook.md)
