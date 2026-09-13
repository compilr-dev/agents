---
title: "validateToolUseResultPairing"
parent: Functions
nav_order: 1
---


# Function: validateToolUseResultPairing()

```ts
function validateToolUseResultPairing(messages): ToolPairingValidation;
```

Defined in: messages/index.ts:120

Validate that tool_result blocks have matching tool_use blocks.
This prevents API errors like "Tool result block missing corresponding tool_use block"

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `messages` | [`Message`](Interface.Message.md)[] | Array of messages to validate |

## Returns

[`ToolPairingValidation`](Interface.ToolPairingValidation.md)

Validation result with details about any mismatches
