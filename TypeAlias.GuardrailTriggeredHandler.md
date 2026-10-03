---
title: "GuardrailTriggeredHandler"
parent: Type Aliases
nav_order: 1
---


# Type Alias: GuardrailTriggeredHandler

```ts
type GuardrailTriggeredHandler = (result, context) => boolean | Promise<boolean>;
```

Defined in: guardrails/types.ts:153

Handler called when a guardrail is triggered

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `result` | [`GuardrailResult`](Interface.GuardrailResult.md) | The guardrail check result |
| `context` | [`GuardrailContext`](Interface.GuardrailContext.md) | Context about the tool call |

## Returns

`boolean` \| `Promise`\<`boolean`\>

true to proceed with execution, false to block
