---
title: "AgentRunResult"
parent: Interfaces
nav_order: 1
---


# Interface: AgentRunResult

Defined in: agent.ts:804

Agent run result

## Properties

### aborted

```ts
aborted: boolean;
```

Defined in: agent.ts:832

Whether the run was aborted

### contextStats?

```ts
optional contextStats?: ContextStats;
```

Defined in: agent.ts:837

Context statistics (if context manager is enabled)

### iterations

```ts
iterations: number;
```

Defined in: agent.ts:818

Number of iterations (tool use loops) executed

### messages

```ts
messages: Message[];
```

Defined in: agent.ts:813

All messages in the conversation

### response

```ts
response: string;
```

Defined in: agent.ts:808

Final text response from the agent

### toolCalls

```ts
toolCalls: {
  input: Record<string, unknown>;
  name: string;
  result: ToolExecutionResult;
}[];
```

Defined in: agent.ts:823

Tool calls made during execution

#### input

```ts
input: Record<string, unknown>;
```

#### name

```ts
name: string;
```

#### result

```ts
result: ToolExecutionResult;
```
