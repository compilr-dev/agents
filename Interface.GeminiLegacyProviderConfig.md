---
title: "GeminiLegacyProviderConfig"
parent: Interfaces
nav_order: 1
---


# Interface: GeminiLegacyProviderConfig

Defined in: providers/gemini.ts:33

Configuration for GeminiProvider

## Properties

### apiKey?

```ts
optional apiKey?: string;
```

Defined in: providers/gemini.ts:35

Google AI API key (falls back to GOOGLE_AI_API_KEY or GEMINI_API_KEY env var)

### baseUrl?

```ts
optional baseUrl?: string;
```

Defined in: providers/gemini.ts:37

Base URL for Gemini API (default: https://generativelanguage.googleapis.com/v1beta/openai)

### maxTokens?

```ts
optional maxTokens?: number;
```

Defined in: providers/gemini.ts:41

Default max tokens (default: 4096)

### model?

```ts
optional model?: string;
```

Defined in: providers/gemini.ts:39

Default model to use (default: gemini-2.0-flash)

### timeout?

```ts
optional timeout?: number;
```

Defined in: providers/gemini.ts:43

Request timeout in milliseconds (default: 120000)
