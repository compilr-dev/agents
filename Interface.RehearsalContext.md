---
title: "RehearsalContext"
parent: Interfaces
nav_order: 1
---


# Interface: RehearsalContext

Defined in: rehearsal/types.ts:165

Context provided to analyzers for better impact assessment

## Properties

### agentContext?

```ts
optional agentContext?: Record<string, unknown>;
```

Defined in: rehearsal/types.ts:194

Additional context from the agent

### currentBranch?

```ts
optional currentBranch?: string;
```

Defined in: rehearsal/types.ts:179

Current git branch (if in a git repo)

### isGitRepo?

```ts
optional isGitRepo?: boolean;
```

Defined in: rehearsal/types.ts:174

Whether we're in a git repository

### sessionModifiedFiles?

```ts
optional sessionModifiedFiles?: string[];
```

Defined in: rehearsal/types.ts:184

Files that have been modified in this session

### sessionStartTime?

```ts
optional sessionStartTime?: Date;
```

Defined in: rehearsal/types.ts:189

Start time of the current session (for time investment calculation)

### workingDirectory

```ts
workingDirectory: string;
```

Defined in: rehearsal/types.ts:169

Working directory for the operation
