---
title: "repairToolPairing"
parent: Functions
nav_order: 1
---


# Function: repairToolPairing()

```ts
function repairToolPairing(messages): Message[];
```

Defined in: messages/index.ts:220

Repair tool use/result pairing issues in a message array.

This function handles BOTH types of orphans with POSITIONAL requirements:
1. Orphaned tool_result blocks (those without a matching tool_use BEFORE them)
   - Causes: "function_response.name: Name cannot be empty" in Gemini
2. Orphaned tool_use blocks (those without tool_result in IMMEDIATELY NEXT message)
   - Causes: "tool_use ids were found without tool_result blocks" in Claude

CRITICAL: Claude API requires tool_result to be in the IMMEDIATELY NEXT message
after the assistant message containing tool_use. This function validates that
positional requirement, not just existence anywhere in the array.

This is particularly useful after context compaction/summarization, which may
remove messages and break tool_use/tool_result pairing.

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `messages` | [`Message`](Interface.Message.md)[] | Array of messages to repair |

## Returns

[`Message`](Interface.Message.md)[]

New array with orphaned tool_use and tool_result blocks removed
