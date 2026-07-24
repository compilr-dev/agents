---
title: "StreamChunk"
parent: Interfaces
nav_order: 1
---


# Interface: StreamChunk

Defined in: providers/types.ts:112

Streaming chunk types

## Properties

### model?

```ts
optional model?: string;
```

Defined in: providers/types.ts:147

Model that generated this response (only present on 'done' chunks)

### stopReason?

```ts
optional stopReason?: string;
```

Defined in: providers/types.ts:156

Stop reason (only present on 'done' chunks).
- 'end_turn': Normal completion
- 'max_tokens': Hit max_tokens limit
- 'refusal': Model refused the request (Claude 4.5+)
- 'context_window_exceeded': Hit context window limit (Claude 4.5+)
- 'tool_use': Model wants to call a tool

### text?

```ts
optional text?: string;
```

Defined in: providers/types.ts:122

### thinking?

```ts
optional thinking?: {
  signature?: string;
  thinking?: string;
};
```

Defined in: providers/types.ts:136

Thinking block data (for thinking_start/thinking_end)

#### signature?

```ts
optional signature?: string;
```

#### thinking?

```ts
optional thinking?: string;
```

### toolUse?

```ts
optional toolUse?: {
  id: string;
  input?: Record<string, unknown>;
  name: string;
  signature?: string;
};
```

Defined in: providers/types.ts:123

#### id

```ts
id: string;
```

#### input?

```ts
optional input?: Record<string, unknown>;
```

#### name

```ts
name: string;
```

#### signature?

```ts
optional signature?: string;
```

Thought signature for Gemini 3 function calls.
Only present on first function call in each step.

### type

```ts
type: 
  | "text"
  | "tool_use_start"
  | "tool_use_delta"
  | "tool_use_end"
  | "thinking_start"
  | "thinking_delta"
  | "thinking_end"
  | "done";
```

Defined in: providers/types.ts:113

### usage?

```ts
optional usage?: LLMUsage;
```

Defined in: providers/types.ts:143

Token usage (only present on 'done' chunks)
