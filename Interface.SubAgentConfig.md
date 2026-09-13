---
title: "SubAgentConfig"
parent: Interfaces
nav_order: 1
---


# Interface: SubAgentConfig

Defined in: agent.ts:843

Configuration for creating a sub-agent

## Properties

### autoDispose?

```ts
optional autoDispose?: boolean;
```

Defined in: agent.ts:897

Automatically dispose the sub-agent after each execution.
This releases memory but requires re-creation for subsequent runs.
Default: false (sub-agent persists for reuse)

### chatOptions?

```ts
optional chatOptions?: ChatOptions;
```

Defined in: agent.ts:884

Chat options override for this sub-agent

### contextBudget?

```ts
optional contextBudget?: number;
```

Defined in: agent.ts:890

Maximum tokens for this sub-agent's context budget.
Default: 25% of parent's context budget.

### contextMode?

```ts
optional contextMode?: "isolated" | "inherited" | "shared";
```

Defined in: agent.ts:867

Context mode for this sub-agent.
- 'isolated': Fresh context, no parent history (default)
- 'inherited': Receives a summary of parent context
- 'shared': Full access to parent context (not recommended for large contexts)

### description?

```ts
optional description?: string;
```

Defined in: agent.ts:853

Description of what this sub-agent specializes in.
Used for automatic delegation decisions.

### inheritPermissions?

```ts
optional inheritPermissions?: boolean;
```

Defined in: agent.ts:935

Inherit parent's permission manager.

When true (default), the sub-agent uses the parent's PermissionManager,
sharing session grants and permission rules. This ensures:
- Sub-agents follow the same permission rules as parent
- Session grants from parent are available to sub-agents
- User sees permission prompts for sub-agent tool usage

Set to false to allow sub-agents to bypass permissions (use with caution).

Default: true

### maxIterations?

```ts
optional maxIterations?: number;
```

Defined in: agent.ts:879

Maximum iterations for this sub-agent (default: 5)

### maxToolResultSize?

```ts
optional maxToolResultSize?: number;
```

Defined in: agent.ts:904

Maximum size (in bytes) for tool result data returned in SubAgentResult.
Larger results are truncated to prevent memory bloat.
Default: 50KB

### name

```ts
name: string;
```

Defined in: agent.ts:847

Unique name for this sub-agent

### stateIsolation?

```ts
optional stateIsolation?: boolean;
```

Defined in: agent.ts:920

Enable state isolation for this sub-agent.

When true, the sub-agent uses an isolated todo store instead of the
shared default store. This prevents state leakage between parallel
sub-agent executions.

Automatically enabled when using runParallelSubAgents().

Inspired by LangGraph issue #6446: Parallel subgraphs with shared
state keys cause InvalidUpdateError.

Default: false (uses shared store)

### systemPrompt?

```ts
optional systemPrompt?: string;
```

Defined in: agent.ts:859

System prompt for this sub-agent.
If not provided, inherits from parent.

### tools?

```ts
optional tools?: Tool<object>[];
```

Defined in: agent.ts:874

Tools available to this sub-agent.
- If not specified, inherits parent's tools
- Can be a subset of parent's tools for safety
