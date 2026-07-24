---
title: "GeminiProviderConfig"
parent: Interfaces
nav_order: 1
---


# Interface: GeminiProviderConfig

Defined in: providers/gemini-native.ts:39

Configuration for GeminiNativeProvider

## Properties

### apiKey

```ts
apiKey: string;
```

Defined in: providers/gemini-native.ts:43

Google AI API key

### estimateTokens?

```ts
optional estimateTokens?: (text) => number;
```

Defined in: providers/gemini-native.ts:62

Optional token estimator function (e.g., tiktoken).
When provided, debug payload reports token counts instead of char-based estimates.
Fallback: Math.ceil(text.length / 4)

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `text` | `string` |

#### Returns

`number`

### maxTokens?

```ts
optional maxTokens?: number;
```

Defined in: providers/gemini-native.ts:55

Default max tokens

#### Default

```ts
4096
```

### model?

```ts
optional model?: string;
```

Defined in: providers/gemini-native.ts:49

Default model to use

#### Default

```ts
'gemini-2.5-flash'
```
