---
title: "AnchorInput"
parent: Interfaces
nav_order: 1
---


# Interface: AnchorInput

Defined in: anchors/types.ts:81

Input for adding a new anchor (id and createdAt are auto-generated if not provided)

## Properties

### content

```ts
content: string;
```

Defined in: anchors/types.ts:83

### expiresAt?

```ts
optional expiresAt?: Date;
```

Defined in: anchors/types.ts:86

### id?

```ts
optional id?: string;
```

Defined in: anchors/types.ts:82

### metadata?

```ts
optional metadata?: Record<string, unknown>;
```

Defined in: anchors/types.ts:88

### priority

```ts
priority: AnchorPriority;
```

Defined in: anchors/types.ts:84

### projectId?

```ts
optional projectId?: string;
```

Defined in: anchors/types.ts:92

Optional project association for project-scoped anchors

### scope

```ts
scope: AnchorScope;
```

Defined in: anchors/types.ts:85

### tags?

```ts
optional tags?: string[];
```

Defined in: anchors/types.ts:87
