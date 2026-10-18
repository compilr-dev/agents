---
title: "AgentAttributes"
parent: Variables
nav_order: 1
---


# Variable: AgentAttributes

```ts
const AgentAttributes: {
  COMPLETED_WITH_TEXT: "agent.completed_with_text";
  ITERATION_MAX: "agent.iteration.max";
  ITERATION_NUMBER: "agent.iteration.number";
  MESSAGE_COUNT: "agent.message_count";
  SESSION_ID: "agent.session_id";
  TOOL_CALL_COUNT: "agent.tool_call_count";
  TOOL_DURATION_MS: "agent.tool.duration_ms";
  TOOL_NAME: "agent.tool.name";
  TOOL_SUCCESS: "agent.tool.success";
};
```

Defined in: tracing/otel-attributes.ts:37

Agent-specific attributes for iteration and tool tracking

## Type Declaration

| Name | Type | Default value | Description | Defined in |
| ------ | ------ | ------ | ------ | ------ |
| <a id="property-completed_with_text"></a> `COMPLETED_WITH_TEXT` | `"agent.completed_with_text"` | `'agent.completed_with_text'` | Whether the iteration completed with text (no tool calls) | tracing/otel-attributes.ts:55 |
| <a id="property-iteration_max"></a> `ITERATION_MAX` | `"agent.iteration.max"` | `'agent.iteration.max'` | Maximum allowed iterations | tracing/otel-attributes.ts:43 |
| <a id="property-iteration_number"></a> `ITERATION_NUMBER` | `"agent.iteration.number"` | `'agent.iteration.number'` | Current iteration number (1-indexed) | tracing/otel-attributes.ts:41 |
| <a id="property-message_count"></a> `MESSAGE_COUNT` | `"agent.message_count"` | `'agent.message_count'` | Number of messages in the conversation | tracing/otel-attributes.ts:53 |
| <a id="property-session_id"></a> `SESSION_ID` | `"agent.session_id"` | `'agent.session_id'` | Session ID for the agent run | tracing/otel-attributes.ts:39 |
| <a id="property-tool_call_count"></a> `TOOL_CALL_COUNT` | `"agent.tool_call_count"` | `'agent.tool_call_count'` | Number of tool calls in the iteration | tracing/otel-attributes.ts:51 |
| <a id="property-tool_duration_ms"></a> `TOOL_DURATION_MS` | `"agent.tool.duration_ms"` | `'agent.tool.duration_ms'` | Tool execution duration in milliseconds | tracing/otel-attributes.ts:49 |
| <a id="property-tool_name"></a> `TOOL_NAME` | `"agent.tool.name"` | `'agent.tool.name'` | Tool name being executed | tracing/otel-attributes.ts:45 |
| <a id="property-tool_success"></a> `TOOL_SUCCESS` | `"agent.tool.success"` | `'agent.tool.success'` | Whether the tool executed successfully | tracing/otel-attributes.ts:47 |
