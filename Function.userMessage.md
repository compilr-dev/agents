---
title: "userMessage"
parent: Functions
nav_order: 1
---


# Function: userMessage()

```ts
function userMessage(content): Message;
```

Defined in: messages/index.ts:23

Create a user message.

⚠️ `string | ContentBlock[]`, like `assistantMessage`. It used to take a plain string only,
which made it unable to build the single most important user message in the whole loop: the
one carrying tool results (`userMessage([toolResultBlock(id, output)])`) — and images, which
also travel as blocks on a user turn. `Message.content` has always allowed both; only this
helper did not, so nine of its own tests could not typecheck and the agent builds those
messages inline instead.

## Parameters

| Parameter | Type |
| ------ | ------ |
| `content` | `string` \| [`ContentBlock`](TypeAlias.ContentBlock.md)[] |

## Returns

[`Message`](Interface.Message.md)
