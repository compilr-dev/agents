---
title: "createGeminiLegacyProvider"
parent: Functions
nav_order: 1
---


# Function: createGeminiLegacyProvider()

```ts
function createGeminiLegacyProvider(config?): GeminiLegacyProvider;
```

Defined in: providers/gemini.ts:192

Create a Gemini provider instance

## Parameters

| Parameter | Type |
| ------ | ------ |
| `config` | [`GeminiLegacyProviderConfig`](Interface.GeminiLegacyProviderConfig.md) |

## Returns

[`GeminiLegacyProvider`](Class.GeminiLegacyProvider.md)

## Example

```typescript
// Using environment variable (GOOGLE_AI_API_KEY or GEMINI_API_KEY)
const provider = createGeminiProvider();

// With explicit API key
const provider = createGeminiProvider({ apiKey: 'AI...' });

// With custom model
const provider = createGeminiProvider({ model: 'gemini-1.5-pro' });

// Available models:
// - gemini-2.0-flash (default, fast)
// - gemini-1.5-flash (faster, cheaper)
// - gemini-1.5-pro (more capable)
```
