---
title: "countTokens"
parent: Functions
nav_order: 1
---


# Function: countTokens()

```ts
function countTokens(text): number;
```

Defined in: utils/tokenizer.ts:57

Count tokens in a text string using tiktoken.
Falls back to chars/4 heuristic for very large or pathologically repetitive strings.

## Parameters

| Parameter | Type |
| ------ | ------ |
| `text` | `string` |

## Returns

`number`
