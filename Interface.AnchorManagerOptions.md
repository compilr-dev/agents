---
title: "AnchorManagerOptions"
parent: Interfaces
nav_order: 1
---


# Interface: AnchorManagerOptions

Defined in: anchors/types.ts:166

Configuration for the AnchorManager

## Properties

### estimateTokens?

```ts
optional estimateTokens?: (content) => number;
```

Defined in: anchors/types.ts:193

Token estimator function (default: rough estimate based on chars)

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `content` | `string` |

#### Returns

`number`

### includeDefaults?

```ts
optional includeDefaults?: boolean;
```

Defined in: anchors/types.ts:188

Include built-in default safety anchors (default: true)

### maxAnchors?

```ts
optional maxAnchors?: number;
```

Defined in: anchors/types.ts:171

Maximum number of anchors to keep (default: 20)
When exceeded, oldest low-priority anchors are removed first

### maxTokens?

```ts
optional maxTokens?: number;
```

Defined in: anchors/types.ts:177

Maximum tokens budget for anchors (default: 2000)
Anchors exceeding this budget are truncated or removed

### persistPath?

```ts
optional persistPath?: string;
```

Defined in: anchors/types.ts:183

Path for persisting anchors (for scope: 'persistent')
If not provided, persistent anchors work like session anchors
