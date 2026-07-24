---
title: "ProjectMemoryOptions"
parent: Interfaces
nav_order: 1
---


# Interface: ProjectMemoryOptions

Defined in: memory/types.ts:74

Options for ProjectMemoryLoader

## Properties

### combineStrategy?

```ts
optional combineStrategy?: CombineStrategy;
```

Defined in: memory/types.ts:116

Strategy for combining multiple memory files

#### Default

```ts
'concat'
```

### customPatterns?

```ts
optional customPatterns?: FilePattern[];
```

Defined in: memory/types.ts:92

Additional custom file patterns to search for

### encoding?

```ts
optional encoding?: BufferEncoding;
```

Defined in: memory/types.ts:147

File encoding

#### Default

```ts
'utf-8'
```

### headerFormat?

```ts
optional headerFormat?: string;
```

Defined in: memory/types.ts:141

Header format template. Use {path} for file path, {relativePath} for relative path

#### Default

```ts
'# From: {relativePath}\n\n'
```

### includeGeneric?

```ts
optional includeGeneric?: boolean;
```

Defined in: memory/types.ts:87

Whether to include generic memory files (PROJECT.md, INSTRUCTIONS.md, AI.md)

#### Default

```ts
true
```

### includeHeaders?

```ts
optional includeHeaders?: boolean;
```

Defined in: memory/types.ts:135

Whether to include file path headers in combined content

#### Default

```ts
true
```

### maxContentSize?

```ts
optional maxContentSize?: number;
```

Defined in: memory/types.ts:129

Maximum total content size in characters
Files are loaded in priority order until limit is reached

#### Default

```ts
100000 (100KB)
```

### maxParentDepth?

```ts
optional maxParentDepth?: number;
```

Defined in: memory/types.ts:104

Maximum number of parent directories to traverse

#### Default

```ts
10
```

### providers?

```ts
optional providers?: string | string[];
```

Defined in: memory/types.ts:81

LLM provider name(s) to search for
E.g., 'claude' will search for CLAUDE.md, .claude.md, .claude/instructions.md
Can be a single provider or array for multi-provider support

#### Default

```ts
'claude'
```

### searchParents?

```ts
optional searchParents?: boolean;
```

Defined in: memory/types.ts:98

Whether to search parent directories up to the root

#### Default

```ts
true
```

### separator?

```ts
optional separator?: string;
```

Defined in: memory/types.ts:122

Separator to use between files when combining

#### Default

```ts
'\n\n---\n\n'
```

### stopAtGitRoot?

```ts
optional stopAtGitRoot?: boolean;
```

Defined in: memory/types.ts:110

Stop searching parents when finding a git root (.git directory)

#### Default

```ts
true
```
