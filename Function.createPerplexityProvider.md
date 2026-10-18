---
title: "createPerplexityProvider"
parent: Functions
nav_order: 1
---


# Function: createPerplexityProvider()

```ts
function createPerplexityProvider(config?): PerplexityProvider;
```

Defined in: providers/perplexity.ts:180

Create a Perplexity provider instance

## Parameters

| Parameter | Type |
| ------ | ------ |
| `config` | [`PerplexityProviderConfig`](Interface.PerplexityProviderConfig.md) |

## Returns

[`PerplexityProvider`](Class.PerplexityProvider.md)

## Example

```typescript
// Using environment variable (PERPLEXITY_API_KEY)
const provider = createPerplexityProvider();

// With explicit API key
const provider = createPerplexityProvider({ apiKey: 'pplx-...' });

// With custom model (sonar models have web search)
const provider = createPerplexityProvider({
  model: 'sonar-pro'
});
```
