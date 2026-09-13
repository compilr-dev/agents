---
title: "StreamWriter"
parent: Type Aliases
nav_order: 1
---


# Type Alias: StreamWriter

```ts
type StreamWriter = (data, metadata?) => void;
```

Defined in: agent.ts:162

Stream writer for emitting custom events during execution.

Tools and middleware can use this to stream custom events to the client.
Inspired by LangGraph's get_stream_writer() pattern.

## Parameters

| Parameter | Type |
| ------ | ------ |
| `data` | `unknown` |
| `metadata?` | `Record`\<`string`, `unknown`\> |

## Returns

`void`

## Example

```typescript
// In a tool executor:
const writer = agent.getStreamWriter();
writer('Processing step 1...', { step: 1 });
// ... do work ...
writer('Processing step 2...', { step: 2 });
```
