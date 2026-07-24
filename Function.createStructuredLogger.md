---
title: "createStructuredLogger"
parent: Functions
nav_order: 1
---


# Function: createStructuredLogger()

```ts
function createStructuredLogger(options?): StructuredLogger;
```

Defined in: tracing/logging.ts:45

Create a structured logger

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `options` | [`StructuredLoggerOptions`](Interface.StructuredLoggerOptions.md) | Logger options |

## Returns

[`StructuredLogger`](Interface.StructuredLogger.md)

StructuredLogger instance

## Example

```typescript
const logger = createStructuredLogger({
  level: 'info',
  serviceName: 'my-agent',
  prettyPrint: process.env.NODE_ENV !== 'production',
});

logger.info('Agent started', { version: '1.0.0' });
logger.error('Tool failed', new Error('timeout'), { toolName: 'bash' });

// Create child logger with context
const sessionLogger = logger.child({ sessionId: 'abc123' });
sessionLogger.info('Processing request'); // includes sessionId
```
