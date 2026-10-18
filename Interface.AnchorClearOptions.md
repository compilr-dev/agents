---
title: "AnchorClearOptions"
parent: Interfaces
nav_order: 1
---


# Interface: AnchorClearOptions

Defined in: anchors/types.ts:135

Options for clearing anchors

## Properties

### expiredOnly?

```ts
optional expiredOnly?: boolean;
```

Defined in: anchors/types.ts:149

Clear only expired anchors

### globalOnly?

```ts
optional globalOnly?: boolean;
```

Defined in: anchors/types.ts:160

If true, only clear global anchors (those without a projectId)
Cannot be used together with projectId

### projectId?

```ts
optional projectId?: string;
```

Defined in: anchors/types.ts:154

Clear only anchors associated with this project

### scope?

```ts
optional scope?: AnchorScope;
```

Defined in: anchors/types.ts:139

Clear only anchors with this scope

### tags?

```ts
optional tags?: string[];
```

Defined in: anchors/types.ts:144

Clear only anchors with these tags
