---
title: "ToolExecutionResult"
parent: Interfaces
nav_order: 1
---


# Interface: ToolExecutionResult

Defined in: tools/types.ts:26

Result of executing a tool

## Properties

### error?

```ts
optional error?: string;
```

Defined in: tools/types.ts:29

### imageBlocks?

```ts
optional imageBlocks?: {
  data: string;
  filename?: string;
  height?: number;
  mediaType: string;
  width?: number;
}[];
```

Defined in: tools/types.ts:36

Optional image blocks to inject alongside the tool result.
When present, these are added as sibling content blocks in the
tool result message, enabling vision-capable LLMs to see images.
Used by tools like view_image that return visual content.

#### data

```ts
data: string;
```

#### filename?

```ts
optional filename?: string;
```

#### height?

```ts
optional height?: number;
```

#### mediaType

```ts
mediaType: string;
```

#### width?

```ts
optional width?: number;
```

### result?

```ts
optional result?: unknown;
```

Defined in: tools/types.ts:28

### success

```ts
success: boolean;
```

Defined in: tools/types.ts:27
