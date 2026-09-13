---
title: "createGroqProvider"
parent: Functions
nav_order: 1
---


# Function: createGroqProvider()

```ts
function createGroqProvider(config?): GroqProvider;
```

Defined in: providers/groq.ts:180

Create a Groq provider instance

## Parameters

| Parameter | Type |
| ------ | ------ |
| `config` | [`GroqProviderConfig`](Interface.GroqProviderConfig.md) |

## Returns

[`GroqProvider`](Class.GroqProvider.md)

## Example

```typescript
// Using environment variable (GROQ_API_KEY)
const provider = createGroqProvider();

// With explicit API key
const provider = createGroqProvider({ apiKey: 'gsk_...' });

// With custom model
const provider = createGroqProvider({
  model: 'llama-3.2-90b-vision-preview'
});
```
