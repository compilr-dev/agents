---
title: "Anchor"
parent: Interfaces
nav_order: 1
---


# Interface: Anchor

Defined in: anchors/types.ts:30

An anchor - critical information that survives context compaction

## Properties

### content

```ts
content: string;
```

Defined in: anchors/types.ts:39

The content to remember (injected into every LLM call)

### createdAt

```ts
createdAt: Date;
```

Defined in: anchors/types.ts:54

When this anchor was created

### expiresAt?

```ts
optional expiresAt?: Date;
```

Defined in: anchors/types.ts:59

When this anchor expires (for temporary anchors)

### id

```ts
id: string;
```

Defined in: anchors/types.ts:34

Unique identifier for this anchor

### metadata?

```ts
optional metadata?: Record<string, unknown>;
```

Defined in: anchors/types.ts:69

Optional metadata for custom use

### priority

```ts
priority: AnchorPriority;
```

Defined in: anchors/types.ts:44

Priority level determines display order and emphasis

### projectId?

```ts
optional projectId?: string;
```

Defined in: anchors/types.ts:75

Optional project association for project-scoped anchors
If not provided, the anchor is considered "global"

### scope

```ts
scope: AnchorScope;
```

Defined in: anchors/types.ts:49

Scope determines lifetime and persistence behavior

### tags?

```ts
optional tags?: string[];
```

Defined in: anchors/types.ts:64

Optional tags for filtering and grouping
