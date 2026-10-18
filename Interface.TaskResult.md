---
title: "TaskResult"
parent: Interfaces
nav_order: 1
---


# Interface: TaskResult

Defined in: tools/builtin/task.ts:76

Result of task tool execution

## Properties

### agentType

```ts
agentType: string;
```

Defined in: tools/builtin/task.ts:85

The agent type that was used

### iterations

```ts
iterations: number;
```

Defined in: tools/builtin/task.ts:90

Number of iterations the sub-agent took

### response

```ts
response: string;
```

Defined in: tools/builtin/task.ts:80

The sub-agent's response

### toolCalls

```ts
toolCalls: number;
```

Defined in: tools/builtin/task.ts:95

Tool calls made by the sub-agent
