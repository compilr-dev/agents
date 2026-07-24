---
title: "maskImageBlock"
parent: Functions
nav_order: 1
---


# Function: maskImageBlock()

```ts
function maskImageBlock(block, turn): TextBlock;
```

Defined in: context/observation-masker.ts:428

Replace an image content block with a text placeholder.
Preserves filename and dimensions for context.

## Parameters

| Parameter | Type |
| ------ | ------ |
| `block` | `ImageBlock` |
| `turn` | `number` |

## Returns

[`TextBlock`](Interface.TextBlock.md)
