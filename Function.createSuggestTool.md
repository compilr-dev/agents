---
title: "createSuggestTool"
parent: Functions
nav_order: 1
---


# Function: createSuggestTool()

```ts
function createSuggestTool(options?): Tool<SuggestInput>;
```

Defined in: tools/builtin/suggest.ts:91

Create a suggest tool with event emission

## Parameters

| Parameter | Type |
| ------ | ------ |
| `options` | [`SuggestToolOptions`](Interface.SuggestToolOptions.md) |

## Returns

[`Tool`](Interface.Tool.md)\<[`SuggestInput`](Interface.SuggestInput.md)\>

## Example

```typescript
const suggestTool = createSuggestTool({
  onSuggest: (event) => {
    // Handle the suggestion (e.g., pass to CLI input prompt)
    console.log('Suggested action:', event.action);
  }
});
agent.registerTool(suggestTool);
```
