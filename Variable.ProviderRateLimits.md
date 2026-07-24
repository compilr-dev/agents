---
title: "ProviderRateLimits"
parent: Variables
nav_order: 1
---


# Variable: ProviderRateLimits

```ts
const ProviderRateLimits: {
  claude: {
     tier1: {
        requestsPerMinute: 50;
        tokensPerMinute: 40000;
     };
     tier2: {
        requestsPerMinute: 1000;
        tokensPerMinute: 80000;
     };
     tier3: {
        requestsPerMinute: 2000;
        tokensPerMinute: 160000;
     };
     tier4: {
        requestsPerMinute: 4000;
        tokensPerMinute: 400000;
     };
  };
  openai: {
     gpt35Turbo: {
        requestsPerMinute: 3500;
        tokensPerMinute: 90000;
     };
     gpt4: {
        requestsPerMinute: 500;
        tokensPerMinute: 10000;
     };
     gpt4Turbo: {
        requestsPerMinute: 500;
        tokensPerMinute: 30000;
     };
  };
};
```

Defined in: rate-limit/provider-wrapper.ts:172

Default rate limits for known providers

## Type Declaration

| Name | Type | Default value | Description | Defined in |
| ------ | ------ | ------ | ------ | ------ |
| <a id="property-claude"></a> `claude` | \{ `tier1`: \{ `requestsPerMinute`: `50`; `tokensPerMinute`: `40000`; \}; `tier2`: \{ `requestsPerMinute`: `1000`; `tokensPerMinute`: `80000`; \}; `tier3`: \{ `requestsPerMinute`: `2000`; `tokensPerMinute`: `160000`; \}; `tier4`: \{ `requestsPerMinute`: `4000`; `tokensPerMinute`: `400000`; \}; \} | - | Anthropic Claude API limits (Tier 1) **See** https://docs.anthropic.com/en/api/rate-limits | rate-limit/provider-wrapper.ts:177 |
| `claude.tier1` | \{ `requestsPerMinute`: `50`; `tokensPerMinute`: `40000`; \} | - | - | rate-limit/provider-wrapper.ts:178 |
| `claude.tier1.requestsPerMinute` | `50` | `50` | - | rate-limit/provider-wrapper.ts:179 |
| `claude.tier1.tokensPerMinute` | `40000` | `40000` | - | rate-limit/provider-wrapper.ts:180 |
| `claude.tier2` | \{ `requestsPerMinute`: `1000`; `tokensPerMinute`: `80000`; \} | - | - | rate-limit/provider-wrapper.ts:182 |
| `claude.tier2.requestsPerMinute` | `1000` | `1000` | - | rate-limit/provider-wrapper.ts:183 |
| `claude.tier2.tokensPerMinute` | `80000` | `80000` | - | rate-limit/provider-wrapper.ts:184 |
| `claude.tier3` | \{ `requestsPerMinute`: `2000`; `tokensPerMinute`: `160000`; \} | - | - | rate-limit/provider-wrapper.ts:186 |
| `claude.tier3.requestsPerMinute` | `2000` | `2000` | - | rate-limit/provider-wrapper.ts:187 |
| `claude.tier3.tokensPerMinute` | `160000` | `160000` | - | rate-limit/provider-wrapper.ts:188 |
| `claude.tier4` | \{ `requestsPerMinute`: `4000`; `tokensPerMinute`: `400000`; \} | - | - | rate-limit/provider-wrapper.ts:190 |
| `claude.tier4.requestsPerMinute` | `4000` | `4000` | - | rate-limit/provider-wrapper.ts:191 |
| `claude.tier4.tokensPerMinute` | `400000` | `400000` | - | rate-limit/provider-wrapper.ts:192 |
| <a id="property-openai"></a> `openai` | \{ `gpt35Turbo`: \{ `requestsPerMinute`: `3500`; `tokensPerMinute`: `90000`; \}; `gpt4`: \{ `requestsPerMinute`: `500`; `tokensPerMinute`: `10000`; \}; `gpt4Turbo`: \{ `requestsPerMinute`: `500`; `tokensPerMinute`: `30000`; \}; \} | - | OpenAI GPT-4 API limits (approximate) | rate-limit/provider-wrapper.ts:199 |
| `openai.gpt35Turbo` | \{ `requestsPerMinute`: `3500`; `tokensPerMinute`: `90000`; \} | - | - | rate-limit/provider-wrapper.ts:208 |
| `openai.gpt35Turbo.requestsPerMinute` | `3500` | `3500` | - | rate-limit/provider-wrapper.ts:209 |
| `openai.gpt35Turbo.tokensPerMinute` | `90000` | `90000` | - | rate-limit/provider-wrapper.ts:210 |
| `openai.gpt4` | \{ `requestsPerMinute`: `500`; `tokensPerMinute`: `10000`; \} | - | - | rate-limit/provider-wrapper.ts:200 |
| `openai.gpt4.requestsPerMinute` | `500` | `500` | - | rate-limit/provider-wrapper.ts:201 |
| `openai.gpt4.tokensPerMinute` | `10000` | `10000` | - | rate-limit/provider-wrapper.ts:202 |
| `openai.gpt4Turbo` | \{ `requestsPerMinute`: `500`; `tokensPerMinute`: `30000`; \} | - | - | rate-limit/provider-wrapper.ts:204 |
| `openai.gpt4Turbo.requestsPerMinute` | `500` | `500` | - | rate-limit/provider-wrapper.ts:205 |
| `openai.gpt4Turbo.tokensPerMinute` | `30000` | `30000` | - | rate-limit/provider-wrapper.ts:206 |
