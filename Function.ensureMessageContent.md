---
title: "ensureMessageContent"
parent: Functions
nav_order: 1
---


# Function: ensureMessageContent()

```ts
function ensureMessageContent(message): Message;
```

Defined in: messages/index.ts:180

Ensure a message has content field (even if empty).
Some APIs (like xAI) require content to be present even when tool_calls exist.

This function handles messages from external sources that might not strictly
conform to our Message type (e.g., API responses with missing content).

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `message` | \| [`Message`](Interface.Message.md) \| \{ `content?`: `string` \| [`ContentBlock`](TypeAlias.ContentBlock.md)[] \| `null`; `role`: `string`; \} | Message to normalize (may have missing content from external APIs) |

## Returns

[`Message`](Interface.Message.md)

Message with guaranteed content field
