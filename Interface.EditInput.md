---
title: "EditInput"
parent: Interfaces
nav_order: 1
---


# Interface: EditInput

Defined in: tools/builtin/edit.ts:14

Input parameters for edit tool

## Properties

### createIfMissing?

```ts
optional createIfMissing?: boolean;
```

Defined in: tools/builtin/edit.ts:38

Create the file if it doesn't exist (default: false)

### filePath

```ts
filePath: string;
```

Defined in: tools/builtin/edit.ts:18

Path to the file to edit

### newString

```ts
newString: string;
```

Defined in: tools/builtin/edit.ts:28

The replacement text

### oldString

```ts
oldString: string;
```

Defined in: tools/builtin/edit.ts:23

The text to search for (must be unique in the file)

### replaceAll?

```ts
optional replaceAll?: boolean;
```

Defined in: tools/builtin/edit.ts:33

Replace all occurrences (default: false, requires unique match)
