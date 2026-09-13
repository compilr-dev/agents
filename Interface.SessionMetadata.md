---
title: "SessionMetadata"
parent: Interfaces
nav_order: 1
---


# Interface: SessionMetadata

Defined in: state/types.ts:80

Metadata stored alongside state for listing/filtering.

## Properties

### createdAt

```ts
createdAt: string;
```

Defined in: state/types.ts:94

Creation timestamp (ISO 8601)

### lastAssistantMessage?

```ts
optional lastAssistantMessage?: string;
```

Defined in: state/types.ts:114

Truncated preview of last assistant message

### lastUserMessage?

```ts
optional lastUserMessage?: string;
```

Defined in: state/types.ts:109

Truncated preview of last user message

### messageCount

```ts
messageCount: number;
```

Defined in: state/types.ts:104

Number of messages in the conversation

### name?

```ts
optional name?: string;
```

Defined in: state/types.ts:89

User-friendly session name

### sessionId

```ts
sessionId: string;
```

Defined in: state/types.ts:84

Session identifier

### tags?

```ts
optional tags?: string[];
```

Defined in: state/types.ts:119

Tags for organization

### updatedAt

```ts
updatedAt: string;
```

Defined in: state/types.ts:99

Last update timestamp (ISO 8601)
