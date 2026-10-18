---
title: "createTogetherProvider"
parent: Functions
nav_order: 1
---


# Function: createTogetherProvider()

```ts
function createTogetherProvider(config?): TogetherProvider;
```

Defined in: providers/together.ts:180

Create a Together AI provider instance

## Parameters

| Parameter | Type |
| ------ | ------ |
| `config` | [`TogetherProviderConfig`](Interface.TogetherProviderConfig.md) |

## Returns

[`TogetherProvider`](Class.TogetherProvider.md)

## Example

```typescript
// Using environment variable (TOGETHER_API_KEY)
const provider = createTogetherProvider();

// With explicit API key
const provider = createTogetherProvider({ apiKey: 'xxx-...' });

// With custom model
const provider = createTogetherProvider({
  model: 'meta-llama/Meta-Llama-3.1-70B-Instruct-Turbo'
});
```
