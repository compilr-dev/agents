---
title: "FileCheckpointerOptions"
parent: Interfaces
nav_order: 1
---


# Interface: FileCheckpointerOptions

Defined in: state/checkpointer.ts:227

Options for FileCheckpointer

## Properties

### extension?

```ts
optional extension?: string;
```

Defined in: state/checkpointer.ts:236

File extension (defaults to '.json')

### serializer?

```ts
optional serializer?: StateSerializer;
```

Defined in: state/checkpointer.ts:231

Custom serializer (defaults to JsonSerializer)
