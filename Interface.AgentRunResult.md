---
title: "AgentRunResult"
parent: Interfaces
nav_order: 1
---


# Interface: AgentRunResult

Defined in: agent.ts:805

Agent run result

## Properties

### aborted

```ts
aborted: boolean;
```

Defined in: agent.ts:833

Whether the run was aborted

### contextStats?

```ts
optional contextStats?: ContextStats;
```

Defined in: agent.ts:838

Context statistics (if context manager is enabled)

### iterations

```ts
iterations: number;
```

Defined in: agent.ts:819

Number of iterations (tool use loops) executed

### messages

```ts
messages: Message[];
```

Defined in: agent.ts:814

All messages in the conversation

### response

```ts
response: string;
```

Defined in: agent.ts:809

Final text response from the agent

### toolCalls

```ts
toolCalls: {
  input: Record<string, unknown>;
  name: string;
  result: ToolExecutionResult;
}[];
```

Defined in: agent.ts:824

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
