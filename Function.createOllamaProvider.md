---
title: "createOllamaProvider"
parent: Functions
nav_order: 1
---


# Function: createOllamaProvider()

```ts
function createOllamaProvider(config?): OllamaProvider;
```

Defined in: providers/ollama.ts:174

Create an Ollama provider instance

## Parameters

| Parameter | Type |
| ------ | ------ |
| `config` | [`OllamaProviderConfig`](Interface.OllamaProviderConfig.md) |

## Returns

[`OllamaProvider`](Class.OllamaProvider.md)

## Example

```typescript
// Default configuration (llama3.1 on localhost:11434)
const provider = createOllamaProvider();

// Custom model
const provider = createOllamaProvider({ model: 'mistral' });

// Custom server
const provider = createOllamaProvider({
  baseUrl: 'http://192.168.1.100:11434',
  model: 'llama3.1:70b'
});
```
