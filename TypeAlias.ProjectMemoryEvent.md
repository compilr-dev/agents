---
title: "ProjectMemoryEvent"
parent: Type Aliases
nav_order: 1
---


# Type Alias: ProjectMemoryEvent

```ts
type ProjectMemoryEvent = 
  | {
  patterns: string[];
  rootDir: string;
  type: "memory:search_start";
}
  | {
  path: string;
  pattern: string;
  type: "memory:file_found";
}
  | {
  file: MemoryFile;
  type: "memory:file_loaded";
}
  | {
  path: string;
  reason: string;
  type: "memory:file_skipped";
}
  | {
  memory: ProjectMemory;
  type: "memory:search_complete";
}
  | {
  error: Error;
  path?: string;
  type: "memory:error";
};
```

Defined in: memory/types.ts:164

Events emitted during memory loading
