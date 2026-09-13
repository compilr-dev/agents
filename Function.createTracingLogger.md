---
title: "createTracingLogger"
parent: Functions
nav_order: 1
---


# Function: createTracingLogger()

```ts
function createTracingLogger(tracingManager, options?): StructuredLogger;
```

Defined in: tracing/logging.ts:324

Create a logger that integrates with TracingManager

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `tracingManager` | \{ `getCurrentSpan`: () => \| \{ `spanId`: `string`; `traceId`: `string`; \} \| `undefined`; \} | TracingManager instance |
| `tracingManager.getCurrentSpan` | () => \| \{ `spanId`: `string`; `traceId`: `string`; \} \| `undefined` | - |
| `options` | [`StructuredLoggerOptions`](Interface.StructuredLoggerOptions.md) | Logger options |

## Returns

[`StructuredLogger`](Interface.StructuredLogger.md)

StructuredLogger that auto-correlates with traces

## Example

```typescript
const tracingManager = new TracingManager({ serviceName: 'my-agent' });
const logger = createTracingLogger(tracingManager);

// Logger automatically includes current trace/span IDs
logger.info('Processing request');
```
