---
title: "SubAgentResult"
parent: Interfaces
nav_order: 1
---


# Interface: SubAgentResult

Defined in: agent.ts:942

Result from a sub-agent execution

## Properties

### contextStats?

```ts
optional contextStats?: ContextStats;
```

Defined in: agent.ts:976

Context stats for the sub-agent's execution

### error?

```ts
optional error?: string;
```

Defined in: agent.ts:961

Error message if execution failed

### iterations

```ts
iterations: number;
```

Defined in: agent.ts:966

Number of iterations used

### name

```ts
name: string;
```

Defined in: agent.ts:946

Name of the sub-agent that executed

### response

```ts
response: string;
```

Defined in: agent.ts:951

Final response from the sub-agent

### success

```ts
success: boolean;
```

Defined in: agent.ts:956

Whether the execution was successful

### toolCalls

```ts
toolCalls: {
  input: Record<string, unknown>;
  name: string;
  result: ToolExecutionResult;
}[];
```

Defined in: agent.ts:971

Tool calls made by the sub-agent

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
