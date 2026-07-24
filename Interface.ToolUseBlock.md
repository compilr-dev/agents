---
title: "ToolUseBlock"
parent: Interfaces
nav_order: 1
---


# Interface: ToolUseBlock

Defined in: providers/types.ts:26

Tool use content block (AI wants to call a tool)

## Properties

### id

```ts
id: string;
```

Defined in: providers/types.ts:28

### input

```ts
input: Record<string, unknown>;
```

Defined in: providers/types.ts:30

### name

```ts
name: string;
```

Defined in: providers/types.ts:29

### signature?

```ts
optional signature?: string;
```

Defined in: providers/types.ts:36

Thought signature for Gemini 3 function calls.
Required for Gemini 3 to maintain reasoning context.

#### See

https://ai.google.dev/gemini-api/docs/thought-signatures

### type

```ts
type: "tool_use";
```

Defined in: providers/types.ts:27
