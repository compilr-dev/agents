---
title: "TracingManagerOptions"
parent: Interfaces
nav_order: 1
---


# Interface: TracingManagerOptions

Defined in: tracing/types.ts:157

Options for creating a TracingManager

## Properties

### autoGenerateTraceId?

```ts
optional autoGenerateTraceId?: boolean;
```

Defined in: tracing/types.ts:167

Whether to auto-generate trace IDs

### defaultAttributes?

```ts
optional defaultAttributes?: SpanAttributes;
```

Defined in: tracing/types.ts:163

Default attributes added to all spans

### maxSpansPerTrace?

```ts
optional maxSpansPerTrace?: number;
```

Defined in: tracing/types.ts:165

Maximum spans per trace (prevents memory issues)

### onEvent?

```ts
optional onEvent?: TracingEventHandler;
```

Defined in: tracing/types.ts:169

Event handler for tracing events

### otelExporter?

```ts
optional otelExporter?: OTelExporter;
```

Defined in: tracing/types.ts:171

Optional OpenTelemetry exporter

### serviceName?

```ts
optional serviceName?: string;
```

Defined in: tracing/types.ts:159

Service name for traces

### serviceVersion?

```ts
optional serviceVersion?: string;
```

Defined in: tracing/types.ts:161

Service version
