---
title: "FormatHintsOptions"
parent: Interfaces
nav_order: 1
---


# Interface: FormatHintsOptions

Defined in: context/file-tracker.ts:89

Options for formatting restoration hints

## Properties

### groupByType?

```ts
optional groupByType?: boolean;
```

Defined in: context/file-tracker.ts:100

Group by access type

#### Default

```ts
true
```

### includeLineCount?

```ts
optional includeLineCount?: boolean;
```

Defined in: context/file-tracker.ts:91

Include line counts for read files

#### Default

```ts
true
```

### includeSummary?

```ts
optional includeSummary?: boolean;
```

Defined in: context/file-tracker.ts:94

Include summaries

#### Default

```ts
false
```

### includeTimestamp?

```ts
optional includeTimestamp?: boolean;
```

Defined in: context/file-tracker.ts:97

Include timestamps

#### Default

```ts
false
```

### maxFiles?

```ts
optional maxFiles?: number;
```

Defined in: context/file-tracker.ts:103

Maximum files to include

#### Default

```ts
20
```

### verbosityLevel?

```ts
optional verbosityLevel?: VerbosityLevel;
```

Defined in: context/file-tracker.ts:106

Verbosity level (adjusts format automatically)
