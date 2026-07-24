---
title: "TaskInput"
parent: Interfaces
nav_order: 1
---


# Interface: TaskInput

Defined in: tools/builtin/task.ts:35

Input parameters for task tool

## Properties

### context\_mode?

```ts
optional context_mode?: ContextMode;
```

Defined in: tools/builtin/task.ts:62

Context inheritance mode (default: from agent type config)
- 'isolated': Fresh context, no parent history
- 'inherit': Receives parent's full message history
- 'inherit-summary': Receives summarized parent context

### description

```ts
description: string;
```

Defined in: tools/builtin/task.ts:39

A short (3-5 word) description of the task

### model?

```ts
optional model?: string;
```

Defined in: tools/builtin/task.ts:54

Optional model to use for this agent (e.g., 'sonnet', 'opus', 'haiku')

### prompt

```ts
prompt: string;
```

Defined in: tools/builtin/task.ts:44

Detailed task prompt for the sub-agent to perform

### subagent\_type

```ts
subagent_type: string;
```

Defined in: tools/builtin/task.ts:49

The type of specialized agent to use (e.g., 'explore', 'code-review', 'general')

### thoroughness?

```ts
optional thoroughness?: ThoroughnessLevel;
```

Defined in: tools/builtin/task.ts:70

Thoroughness level for exploration agents (default: 'medium')
- 'quick': Fast searches, basic analysis
- 'medium': Balanced depth and speed
- 'thorough': Comprehensive analysis, multiple passes
