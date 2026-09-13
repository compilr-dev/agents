---
title: "ListSessionsOptions"
parent: Interfaces
nav_order: 1
---


# Interface: ListSessionsOptions

Defined in: state/types.ts:206

Options for listing sessions.

## Properties

### limit?

```ts
optional limit?: number;
```

Defined in: state/types.ts:210

Maximum number of sessions to return

### offset?

```ts
optional offset?: number;
```

Defined in: state/types.ts:215

Number of sessions to skip (for pagination)

### order?

```ts
optional order?: "asc" | "desc";
```

Defined in: state/types.ts:225

Sort direction

### orderBy?

```ts
optional orderBy?: "createdAt" | "updatedAt";
```

Defined in: state/types.ts:220

Field to sort by

### tags?

```ts
optional tags?: string[];
```

Defined in: state/types.ts:230

Filter by tags (sessions must have all specified tags)
