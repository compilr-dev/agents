---
title: "AnchorQueryOptions"
parent: Interfaces
nav_order: 1
---


# Interface: AnchorQueryOptions

Defined in: anchors/types.ts:98

Options for querying anchors

## Properties

### globalOnly?

```ts
optional globalOnly?: boolean;
```

Defined in: anchors/types.ts:129

If true, only return global anchors (those without a projectId)
Cannot be used together with projectId

### includeExpired?

```ts
optional includeExpired?: boolean;
```

Defined in: anchors/types.ts:117

Include expired temporary anchors (default: false)

### priority?

```ts
optional priority?: AnchorPriority;
```

Defined in: anchors/types.ts:102

Filter by priority level

### projectId?

```ts
optional projectId?: string;
```

Defined in: anchors/types.ts:123

Filter by project ID
Only returns anchors associated with this project

### scope?

```ts
optional scope?: AnchorScope;
```

Defined in: anchors/types.ts:107

Filter by scope

### tags?

```ts
optional tags?: string[];
```

Defined in: anchors/types.ts:112

Filter by tags (anchors must have ALL specified tags)
