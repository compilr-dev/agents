---
title: "GenAIAttributes"
parent: Variables
nav_order: 1
---


# Variable: GenAIAttributes

```ts
const GenAIAttributes: {
  OPERATION_NAME: "gen_ai.operation.name";
  REQUEST_MAX_TOKENS: "gen_ai.request.max_tokens";
  REQUEST_MODEL: "gen_ai.request.model";
  REQUEST_TEMPERATURE: "gen_ai.request.temperature";
  RESPONSE_FINISH_REASON: "gen_ai.response.finish_reasons";
  RESPONSE_MODEL: "gen_ai.response.model";
  SYSTEM: "gen_ai.system";
  USAGE_INPUT_TOKENS: "gen_ai.usage.input_tokens";
  USAGE_OUTPUT_TOKENS: "gen_ai.usage.output_tokens";
};
```

Defined in: tracing/otel-attributes.ts:13

gen_ai.* semantic convention attributes for LLM operations

## Type Declaration

| Name | Type | Default value | Description | Defined in |
| ------ | ------ | ------ | ------ | ------ |
| <a id="property-operation_name"></a> `OPERATION_NAME` | `"gen_ai.operation.name"` | `'gen_ai.operation.name'` | The operation name (e.g. 'chat') | tracing/otel-attributes.ts:17 |
| <a id="property-request_max_tokens"></a> `REQUEST_MAX_TOKENS` | `"gen_ai.request.max_tokens"` | `'gen_ai.request.max_tokens'` | Max tokens requested | tracing/otel-attributes.ts:21 |
| <a id="property-request_model"></a> `REQUEST_MODEL` | `"gen_ai.request.model"` | `'gen_ai.request.model'` | The model requested | tracing/otel-attributes.ts:19 |
| <a id="property-request_temperature"></a> `REQUEST_TEMPERATURE` | `"gen_ai.request.temperature"` | `'gen_ai.request.temperature'` | Temperature requested | tracing/otel-attributes.ts:23 |
| <a id="property-response_finish_reason"></a> `RESPONSE_FINISH_REASON` | `"gen_ai.response.finish_reasons"` | `'gen_ai.response.finish_reasons'` | Finish reasons (e.g. ['stop'], ['tool_calls']) | tracing/otel-attributes.ts:27 |
| <a id="property-response_model"></a> `RESPONSE_MODEL` | `"gen_ai.response.model"` | `'gen_ai.response.model'` | The model actually used in the response | tracing/otel-attributes.ts:25 |
| <a id="property-system"></a> `SYSTEM` | `"gen_ai.system"` | `'gen_ai.system'` | The AI system (e.g. 'anthropic', 'openai', 'google') | tracing/otel-attributes.ts:15 |
| <a id="property-usage_input_tokens"></a> `USAGE_INPUT_TOKENS` | `"gen_ai.usage.input_tokens"` | `'gen_ai.usage.input_tokens'` | Input token count | tracing/otel-attributes.ts:29 |
| <a id="property-usage_output_tokens"></a> `USAGE_OUTPUT_TOKENS` | `"gen_ai.usage.output_tokens"` | `'gen_ai.usage.output_tokens'` | Output token count | tracing/otel-attributes.ts:31 |
