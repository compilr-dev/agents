---
title: "createOpenRouterProvider"
parent: Functions
nav_order: 1
---


# Function: createOpenRouterProvider()

```ts
function createOpenRouterProvider(config?): OpenRouterProvider;
```

Defined in: providers/openrouter.ts:201

Create an OpenRouter provider instance

## Parameters

| Parameter | Type |
| ------ | ------ |
| `config` | [`OpenRouterProviderConfig`](Interface.OpenRouterProviderConfig.md) |

## Returns

[`OpenRouterProvider`](Class.OpenRouterProvider.md)

## Example

```typescript
// Using environment variable (OPENROUTER_API_KEY)
const provider = createOpenRouterProvider();

// With explicit API key
const provider = createOpenRouterProvider({ apiKey: 'sk-or-...' });

// With custom model and site attribution
const provider = createOpenRouterProvider({
  model: 'anthropic/claude-sonnet-4-6',
  siteUrl: 'https://myapp.com',
  siteName: 'My App'
});
```
