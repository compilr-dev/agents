---
title: "GrepInput"
parent: Interfaces
nav_order: 1
---


# Interface: GrepInput

Defined in: tools/builtin/grep.ts:38

Input parameters for grep tool

## Properties

### after?

```ts
optional after?: number;
```

Defined in: tools/builtin/grep.ts:67

Number of context lines after match (default: 0)

### before?

```ts
optional before?: number;
```

Defined in: tools/builtin/grep.ts:62

Number of context lines before match (default: 0)

### excludeDirs?

```ts
optional excludeDirs?: string[];
```

Defined in: tools/builtin/grep.ts:99

Directory names to exclude from search.
Default excludes: node_modules, .git, dist, build, etc.
Set to empty array [] to include all directories.

### extensions?

```ts
optional extensions?: string[];
```

Defined in: tools/builtin/grep.ts:82

File extensions to include (e.g., ['.ts', '.js'])

### filesOnly?

```ts
optional filesOnly?: boolean;
```

Defined in: tools/builtin/grep.ts:72

Only return filenames with matches (default: false)

### ignoreCase?

```ts
optional ignoreCase?: boolean;
```

Defined in: tools/builtin/grep.ts:52

Case insensitive search (default: false)

### includeHidden?

```ts
optional includeHidden?: boolean;
```

Defined in: tools/builtin/grep.ts:77

Include hidden files/directories (default: false)

### lineNumbers?

```ts
optional lineNumbers?: boolean;
```

Defined in: tools/builtin/grep.ts:57

Include line numbers in output (default: true)

### maxMatches?

```ts
optional maxMatches?: number;
```

Defined in: tools/builtin/grep.ts:87

Maximum number of matches to return (default: 100)

### path

```ts
path: string;
```

Defined in: tools/builtin/grep.ts:47

Path to file or directory to search in

### pattern

```ts
pattern: string;
```

Defined in: tools/builtin/grep.ts:42

Regular expression pattern to search for

### recursive?

```ts
optional recursive?: boolean;
```

Defined in: tools/builtin/grep.ts:92

Search recursively in directories (default: true)
