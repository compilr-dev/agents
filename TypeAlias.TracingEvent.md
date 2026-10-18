---
title: "TracingEvent"
parent: Type Aliases
nav_order: 1
---


# Type Alias: TracingEvent

```ts
type TracingEvent = 
  | {
  timestamp: number;
  traceId: string;
  type: "trace:started";
}
  | {
  durationMs: number;
  spanCount: number;
  traceId: string;
  type: "trace:ended";
}
  | {
  name: string;
  parentSpanId?: string;
  spanId: string;
  traceId: string;
  type: "span:started";
}
  | {
  durationMs: number;
  spanId: string;
  status: SpanStatus;
  traceId: string;
  type: "span:ended";
}
  | {
  eventName: string;
  spanId: string;
  traceId: string;
  type: "span:event";
}
  | {
  error: Error;
  spanId: string;
  traceId: string;
  type: "span:error";
}
  | {
  exporter: string;
  traceId: string;
  type: "export:success";
}
  | {
  error: Error;
  exporter: string;
  traceId: string;
  type: "export:error";
};
```

Defined in: tracing/types.ts:211

Events emitted by TracingManager
