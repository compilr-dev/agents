---
title: "SemanticAttributes"
parent: Variables
nav_order: 1
---


# Variable: SemanticAttributes

```ts
const SemanticAttributes: {
  AGENT_ITERATION: "agent.iteration";
  AGENT_MAX_ITERATIONS: "agent.max_iterations";
  AGENT_SESSION_ID: "agent.session_id";
  ERROR_MESSAGE: "error.message";
  ERROR_STACK: "error.stack";
  ERROR_TYPE: "error.type";
  LLM_CACHE_CREATION_TOKENS: "llm.cache_creation_tokens";
  LLM_CACHE_READ_TOKENS: "llm.cache_read_tokens";
  LLM_INPUT_TOKENS: "llm.input_tokens";
  LLM_MODEL: "llm.model";
  LLM_OUTPUT_TOKENS: "llm.output_tokens";
  LLM_PROVIDER: "llm.provider";
  LLM_TOTAL_TOKENS: "llm.total_tokens";
  MESSAGE_COUNT: "message.count";
  MESSAGE_ROLE: "message.role";
  TOOL_ERROR: "tool.error";
  TOOL_INPUT: "tool.input";
  TOOL_NAME: "tool.name";
  TOOL_RESULT: "tool.result";
  TOOL_SUCCESS: "tool.success";
};
```

Defined in: tracing/types.ts:118

Standard attribute names following OpenTelemetry semantic conventions

## Type Declaration

| Name | Type | Default value | Defined in |
| ------ | ------ | ------ | ------ |
| <a id="property-agent_iteration"></a> `AGENT_ITERATION` | `"agent.iteration"` | `'agent.iteration'` | tracing/types.ts:121 |
| <a id="property-agent_max_iterations"></a> `AGENT_MAX_ITERATIONS` | `"agent.max_iterations"` | `'agent.max_iterations'` | tracing/types.ts:122 |
| <a id="property-agent_session_id"></a> `AGENT_SESSION_ID` | `"agent.session_id"` | `'agent.session_id'` | tracing/types.ts:120 |
| <a id="property-error_message"></a> `ERROR_MESSAGE` | `"error.message"` | `'error.message'` | tracing/types.ts:146 |
| <a id="property-error_stack"></a> `ERROR_STACK` | `"error.stack"` | `'error.stack'` | tracing/types.ts:147 |
| <a id="property-error_type"></a> `ERROR_TYPE` | `"error.type"` | `'error.type'` | tracing/types.ts:145 |
| <a id="property-llm_cache_creation_tokens"></a> `LLM_CACHE_CREATION_TOKENS` | `"llm.cache_creation_tokens"` | `'llm.cache_creation_tokens'` | tracing/types.ts:131 |
| <a id="property-llm_cache_read_tokens"></a> `LLM_CACHE_READ_TOKENS` | `"llm.cache_read_tokens"` | `'llm.cache_read_tokens'` | tracing/types.ts:130 |
| <a id="property-llm_input_tokens"></a> `LLM_INPUT_TOKENS` | `"llm.input_tokens"` | `'llm.input_tokens'` | tracing/types.ts:127 |
| <a id="property-llm_model"></a> `LLM_MODEL` | `"llm.model"` | `'llm.model'` | tracing/types.ts:126 |
| <a id="property-llm_output_tokens"></a> `LLM_OUTPUT_TOKENS` | `"llm.output_tokens"` | `'llm.output_tokens'` | tracing/types.ts:128 |
| <a id="property-llm_provider"></a> `LLM_PROVIDER` | `"llm.provider"` | `'llm.provider'` | tracing/types.ts:125 |
| <a id="property-llm_total_tokens"></a> `LLM_TOTAL_TOKENS` | `"llm.total_tokens"` | `'llm.total_tokens'` | tracing/types.ts:129 |
| <a id="property-message_count"></a> `MESSAGE_COUNT` | `"message.count"` | `'message.count'` | tracing/types.ts:142 |
| <a id="property-message_role"></a> `MESSAGE_ROLE` | `"message.role"` | `'message.role'` | tracing/types.ts:141 |
| <a id="property-tool_error"></a> `TOOL_ERROR` | `"tool.error"` | `'tool.error'` | tracing/types.ts:137 |
| <a id="property-tool_input"></a> `TOOL_INPUT` | `"tool.input"` | `'tool.input'` | tracing/types.ts:135 |
| <a id="property-tool_name"></a> `TOOL_NAME` | `"tool.name"` | `'tool.name'` | tracing/types.ts:134 |
| <a id="property-tool_result"></a> `TOOL_RESULT` | `"tool.result"` | `'tool.result'` | tracing/types.ts:138 |
| <a id="property-tool_success"></a> `TOOL_SUCCESS` | `"tool.success"` | `'tool.success'` | tracing/types.ts:136 |
