---
title: "AgentTypeConfig"
parent: Interfaces
nav_order: 1
---


# Interface: AgentTypeConfig

Defined in: tools/builtin/task.ts:101

Configuration for a pre-defined agent type

## Properties

### allowedTools?

```ts
optional allowedTools?: string[];
```

Defined in: tools/builtin/task.ts:153

Tool names to allow (whitelist) when toolInheritance is 'filter'

### contextMode?

```ts
optional contextMode?: ContextMode;
```

Defined in: tools/builtin/task.ts:135

Default context inheritance mode

### defaultModel?

```ts
optional defaultModel?: string;
```

Defined in: tools/builtin/task.ts:130

Default model for this agent type

### deniedTools?

```ts
optional deniedTools?: string[];
```

Defined in: tools/builtin/task.ts:158

Tool names to deny (blacklist) when toolInheritance is 'filter'

### description

```ts
description: string;
```

Defined in: tools/builtin/task.ts:105

Description of what this agent type does

### maxIterations?

```ts
optional maxIterations?: number;
```

Defined in: tools/builtin/task.ts:125

Maximum iterations for this agent type

### skills?

```ts
optional skills?: string[];
```

Defined in: tools/builtin/task.ts:120

Skills available to this agent type

### supportsThoroughness?

```ts
optional supportsThoroughness?: boolean;
```

Defined in: tools/builtin/task.ts:140

Whether this agent type supports thoroughness levels

### systemPrompt?

```ts
optional systemPrompt?: string;
```

Defined in: tools/builtin/task.ts:110

System prompt for this agent type

### toolInheritance?

```ts
optional toolInheritance?: "filter" | "none" | "all";
```

Defined in: tools/builtin/task.ts:148

Tool inheritance mode:
- 'none': Only use tools specified in this config
- 'all': Inherit all parent tools plus config tools
- 'filter': Inherit parent tools filtered by allowedTools/deniedTools

### tools?

```ts
optional tools?: (string | Tool<object>)[];
```

Defined in: tools/builtin/task.ts:115

Tools available to this agent type (tool names or Tool instances)
