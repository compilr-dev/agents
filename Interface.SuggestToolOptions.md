---
title: "SuggestToolOptions"
parent: Interfaces
nav_order: 1
---


# Interface: SuggestToolOptions

Defined in: tools/builtin/suggest.ts:35

Options for creating the suggest tool

## Properties

### onSuggest?

```ts
optional onSuggest?: (event) => void;
```

Defined in: tools/builtin/suggest.ts:40

Callback to emit suggest event
The CLI captures this to display the suggestion

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `event` | \{ `action`: `string`; `reason?`: `string`; `type`: `"suggest"`; \} |
| `event.action` | `string` |
| `event.reason?` | `string` |
| `event.type` | `"suggest"` |

#### Returns

`void`
