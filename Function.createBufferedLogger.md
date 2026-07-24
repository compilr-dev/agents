---
title: "createBufferedLogger"
parent: Functions
nav_order: 1
---


# Function: createBufferedLogger()

```ts
function createBufferedLogger(): StructuredLogger & {
  clear: () => void;
  entries: LogEntry[];
};
```

Defined in: tracing/logging.ts:242

Create a logger that buffers entries (useful for testing)

## Returns

[`StructuredLogger`](Interface.StructuredLogger.md) & \{
  `clear`: () => `void`;
  `entries`: [`LogEntry`](Interface.LogEntry.md)[];
\}
