---
title: "ClaudeProviderConfig"
parent: Interfaces
nav_order: 1
---


# Interface: ClaudeProviderConfig

Defined in: providers/claude.ts:88

Configuration for ClaudeProvider

## Properties

### apiKey

```ts
apiKey: string;
```

Defined in: providers/claude.ts:92

Anthropic API key

### baseURL?

```ts
optional baseURL?: string;
```

Defined in: providers/claude.ts:103

Base URL for API (useful for proxies)

### enableExtendedContext?

```ts
optional enableExtendedContext?: boolean;
```

Defined in: providers/claude.ts:145

Enable extended context window (1M tokens for supported Claude models).
Sends `context-1m-2025-08-07` beta header.
Long-context pricing applies above 200K tokens per request.

#### Default

```ts
false
```

### enablePromptCaching?

```ts
optional enablePromptCaching?: boolean;
```

Defined in: providers/claude.ts:122

Enable prompt caching for system prompt and tools.

When enabled, the system prompt and tool definitions are cached
server-side, reducing token costs by up to 90% on subsequent requests.

- Cache write: 1.25x base input cost (first request)
- Cache read: 0.1x base input cost (subsequent requests within 5 min)

#### Default

```ts
true
```

### enableTokenEfficientTools?

```ts
optional enableTokenEfficientTools?: boolean;
```

Defined in: providers/claude.ts:130

Enable token-efficient tool use (Anthropic beta).
Sends compact tool representation, reducing input tokens.
No-op for Claude 4+ (already default).

#### Default

```ts
true
```

### estimateTokens?

```ts
optional estimateTokens?: (text) => number;
```

Defined in: providers/claude.ts:137

Optional token estimator function (e.g., tiktoken).
When provided, debug payload reports token counts instead of char-based estimates.
Fallback: Math.ceil(text.length / 4)

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `text` | `string` |

#### Returns

`number`

### maxRetries?

```ts
optional maxRetries?: number;
```

Defined in: providers/claude.ts:162

SDK-level retries. Defaults to 0 because the agent loop does its own
retry with backoff (`withRetryGenerator`, emitting `llm_retry` events) —
leaving the SDK's built-in retries on would double up and each stalled
attempt would eat the full timeout before our layer ever sees the error.

#### Default

```ts
0
```

### maxTokens?

```ts
optional maxTokens?: number;
```

Defined in: providers/claude.ts:109

Default max tokens

#### Default

```ts
4096
```

### model?

```ts
optional model?: string;
```

Defined in: providers/claude.ts:98

Default model to use

#### Default

```ts
'claude-sonnet-5'
```

### timeout?

```ts
optional timeout?: number;
```

Defined in: providers/claude.ts:153

Per-request timeout in milliseconds. Without this the Anthropic SDK
default (~10 min) lets a STALLED request (network dropped mid-call) hang
far too long before it errors. Matches the openai/groq/fireworks providers.

#### Default

```ts
120000
```
