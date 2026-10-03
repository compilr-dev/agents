---
title: "createFireworksProvider"
parent: Functions
nav_order: 1
---


# Function: createFireworksProvider()

```ts
function createFireworksProvider(config?): FireworksProvider;
```

Defined in: providers/fireworks.ts:196

Create a Fireworks AI provider instance

## Parameters

| Parameter | Type |
| ------ | ------ |
| `config` | [`FireworksProviderConfig`](Interface.FireworksProviderConfig.md) |

## Returns

[`FireworksProvider`](Class.FireworksProvider.md)

## Example

```typescript
// Using environment variable (FIREWORKS_API_KEY)
const provider = createFireworksProvider();

// With explicit API key
const provider = createFireworksProvider({ apiKey: 'fw_...' });

// With custom model
const provider = createFireworksProvider({
  model: 'accounts/fireworks/models/llama-v3p1-70b-instruct'
});
```
