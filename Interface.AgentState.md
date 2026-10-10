---
title: "AgentState"
parent: Interfaces
nav_order: 1
---


# Interface: AgentState

Defined in: state/types.ts:19

Serializable snapshot of an agent's current state.
Contains everything needed to resume a conversation.

## Properties

### createdAt

```ts
createdAt: string;
```

Defined in: state/types.ts:64

When the session was created (ISO 8601)

### currentIteration

```ts
currentIteration: number;
```

Defined in: state/types.ts:48

Current iteration count

### messages

```ts
messages: Message[];
```

Defined in: state/types.ts:28

Conversation messages

### model?

```ts
optional model?: string;
```

Defined in: state/types.ts:38

Model identifier (optional, for resume)

### sessionId

```ts
sessionId: string;
```

Defined in: state/types.ts:23

Unique session identifier

### systemPrompt

```ts
systemPrompt: string;
```

Defined in: state/types.ts:33

System prompt (needed for resume)

### todos

```ts
todos: TodoItem[];
```

Defined in: state/types.ts:43

Todo items state

### totalTokensUsed

```ts
totalTokensUsed: number;
```

Defined in: state/types.ts:59

Total tokens used in the session

### turnCount

```ts
turnCount: number;
```

Defined in: state/types.ts:54

Number of conversation turns (user + assistant exchanges)
Used by context manager to track recent vs old messages for compaction.

### updatedAt

```ts
updatedAt: string;
```

Defined in: state/types.ts:69

When the session was last updated (ISO 8601)

### version

```ts
version: number;
```

Defined in: state/types.ts:74

Schema version for migration support
