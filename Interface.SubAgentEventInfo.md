---
title: "SubAgentEventInfo"
parent: Interfaces
nav_order: 1
---


# Interface: SubAgentEventInfo

Defined in: tools/builtin/task.ts:164

Sub-agent event with source information

## Properties

### agentName

```ts
agentName: string;
```

Defined in: tools/builtin/task.ts:168

Name of the sub-agent that emitted this event

### agentType

```ts
agentType: string;
```

Defined in: tools/builtin/task.ts:173

Type of the sub-agent

### event

```ts
event: AgentEvent;
```

Defined in: tools/builtin/task.ts:183

The original event from the sub-agent

### toolUseId?

```ts
optional toolUseId?: string;
```

Defined in: tools/builtin/task.ts:178

Tool use ID for correlation with parent tool call
