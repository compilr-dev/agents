---
title: "ToolRegistryOptions"
parent: Interfaces
nav_order: 1
---


# Interface: ToolRegistryOptions

Defined in: tools/registry.ts:26

Options for creating a DefaultToolRegistry

## Properties

### defaultTimeoutMs?

```ts
optional defaultTimeoutMs?: number;
```

Defined in: tools/registry.ts:31

Default timeout for tool execution in milliseconds.
Default: 30000 (30 seconds). Set to 0 to disable timeout.

### fallbackHandler?

```ts
optional fallbackHandler?: ToolFallbackHandler;
```

Defined in: tools/registry.ts:42

Fallback handler for tools not found in the primary registry.
Enables transparent routing to secondary registries (e.g., meta-tools).

### toolTimeouts?

```ts
optional toolTimeouts?: Record<string, number>;
```

Defined in: tools/registry.ts:36

Per-tool timeout overrides (tool name -> timeout in ms)
