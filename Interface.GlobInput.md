---
title: "GlobInput"
parent: Interfaces
nav_order: 1
---


# Interface: GlobInput

Defined in: tools/builtin/glob.ts:38

Input parameters for glob tool

## Properties

### absolute?

```ts
optional absolute?: boolean;
```

Defined in: tools/builtin/glob.ts:77

Return absolute paths instead of relative (default: false)

### excludeDirs?

```ts
optional excludeDirs?: string[];
```

Defined in: tools/builtin/glob.ts:84

Directory names to exclude from search.
Default excludes: node_modules, .git, dist, build, etc.
Set to empty array [] to include all directories.

### includeHidden?

```ts
optional includeHidden?: boolean;
```

Defined in: tools/builtin/glob.ts:52

Include hidden files and directories (default: false)

### maxDepth?

```ts
optional maxDepth?: number;
```

Defined in: tools/builtin/glob.ts:67

Maximum depth to traverse (default: unlimited)

### maxResults?

```ts
optional maxResults?: number;
```

Defined in: tools/builtin/glob.ts:72

Maximum number of results (default: 1000)

### onlyDirectories?

```ts
optional onlyDirectories?: boolean;
```

Defined in: tools/builtin/glob.ts:57

Only match directories (default: false)

### onlyFiles?

```ts
optional onlyFiles?: boolean;
```

Defined in: tools/builtin/glob.ts:62

Only match files (default: true)

### path?

```ts
optional path?: string;
```

Defined in: tools/builtin/glob.ts:47

Base directory to search in (default: current directory)

### pattern

```ts
pattern: string;
```

Defined in: tools/builtin/glob.ts:42

Glob pattern to match files against (e.g., "**/*.ts", "src/*.js")
