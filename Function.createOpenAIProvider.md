---
title: "createOpenAIProvider"
parent: Functions
nav_order: 1
---


# Function: createOpenAIProvider()

```ts
function createOpenAIProvider(config?): OpenAIProvider;
```

Defined in: providers/openai.ts:311

Create an OpenAI provider instance.

## Parameters

| Parameter | Type |
| ------ | ------ |
| `config` | [`OpenAIProviderConfig`](Interface.OpenAIProviderConfig.md) |

## Returns

[`OpenAIProvider`](Class.OpenAIProvider.md)

## Example

```typescript
// Using environment variable (OPENAI_API_KEY)
const provider = createOpenAIProvider();

// With explicit API key
const provider = createOpenAIProvider({ apiKey: 'sk-...' });

// With a specific model — the transport follows from the id
const provider = createOpenAIProvider({ model: 'gpt-6-astra' });

// With organization
const provider = createOpenAIProvider({ apiKey: 'sk-...', organization: 'org-...' });
```
