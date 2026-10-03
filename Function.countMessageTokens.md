---
title: "countMessageTokens"
parent: Functions
nav_order: 1
---


# Function: countMessageTokens()

```ts
function countMessageTokens(messages): number;
```

Defined in: utils/tokenizer.ts:75

Count tokens across an array of messages

Extracts all text content from messages (text blocks, tool inputs/results,
thinking blocks) and counts tokens using tiktoken.

## Parameters

| Parameter | Type |
| ------ | ------ |
| `messages` | [`Message`](Interface.Message.md)[] |

## Returns

`number`
