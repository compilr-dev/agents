---
title: "SessionInfo"
parent: Interfaces
nav_order: 1
---


# Interface: SessionInfo

Defined in: state/types.ts:125

Lightweight session info for listing (without full state).

## Properties

### createdAt

```ts
createdAt: string;
```

Defined in: state/types.ts:139

Creation timestamp (ISO 8601)

### messageCount

```ts
messageCount: number;
```

Defined in: state/types.ts:149

Number of messages

### name?

```ts
optional name?: string;
```

Defined in: state/types.ts:134

User-friendly session name

### preview?

```ts
optional preview?: string;
```

Defined in: state/types.ts:154

Preview text (last message truncated)

### sessionId

```ts
sessionId: string;
```

Defined in: state/types.ts:129

Session identifier

### tags?

```ts
optional tags?: string[];
```

Defined in: state/types.ts:159

Tags for organization

### updatedAt

```ts
updatedAt: string;
```

Defined in: state/types.ts:144

Last update timestamp (ISO 8601)
