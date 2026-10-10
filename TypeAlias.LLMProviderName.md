---
title: "LLMProviderName"
parent: Type Aliases
nav_order: 1
---


# Type Alias: LLMProviderName

```ts
type LLMProviderName = string;
```

Defined in: memory/types.ts:17

LLM provider name for memory file discovery.

Common values: 'claude', 'gemini', 'openai', 'gpt', 'copilot', 'cursor', 'codeium', 'anthropic'

Can be any string to support custom providers - patterns will be generated
automatically (e.g., 'myai' -> MYAI.md, .myai.md, .myai/instructions.md)
