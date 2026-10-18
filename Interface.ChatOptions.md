---
title: "ChatOptions"
parent: Interfaces
nav_order: 1
---


# Interface: ChatOptions

Defined in: providers/types.ts:205

Options for chat requests

## Properties

### enablePromptCaching?

```ts
optional enablePromptCaching?: boolean;
```

Defined in: providers/types.ts:242

Enable prompt caching for system prompt and tools (Claude-specific)

When enabled, the system prompt and tool definitions are cached
server-side, reducing token costs by up to 90% on subsequent requests.

- Cache write: 1.25x base input cost (first request)
- Cache read: 0.1x base input cost (subsequent requests within 5 min)

#### Default

```ts
Provider-level setting (typically true)
```

### maxTokens?

```ts
optional maxTokens?: number;
```

Defined in: providers/types.ts:207

### model?

```ts
optional model?: string;
```

Defined in: providers/types.ts:206

### signal?

```ts
optional signal?: AbortSignal;
```

Defined in: providers/types.ts:229

AbortSignal for cancelling the LLM request.
When aborted, the provider should stop streaming and throw/return immediately.

### stopSequences?

```ts
optional stopSequences?: string[];
```

Defined in: providers/types.ts:209

### temperature?

```ts
optional temperature?: number;
```

Defined in: providers/types.ts:208

### thinking?

```ts
optional thinking?: ThinkingConfig;
```

Defined in: providers/types.ts:223

Extended thinking configuration (Claude-specific)

When enabled, Claude will show its reasoning process before
providing the final response. Requires budget_tokens >= 1024.

#### Example

```typescript
thinking: { type: 'enabled', budgetTokens: 10000 }
```

### tools?

```ts
optional tools?: ToolDefinition[];
```

Defined in: providers/types.ts:210
