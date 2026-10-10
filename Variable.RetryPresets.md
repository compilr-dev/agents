---
title: "RetryPresets"
parent: Variables
nav_order: 1
---


# Variable: RetryPresets

```ts
const RetryPresets: {
  aggressive: () => RetryConfig;
  conservative: () => RetryConfig;
  none: () => RetryConfig;
  respectful: () => RetryConfig;
};
```

Defined in: rate-limit/retry.ts:226

Retry configuration builder for common scenarios

## Type Declaration

| Name | Type | Description | Defined in |
| ------ | ------ | ------ | ------ |
| <a id="property-aggressive"></a> `aggressive()` | () => [`RetryConfig`](Interface.RetryConfig.md) | Aggressive retry: more retries, shorter delays | rate-limit/retry.ts:241 |
| <a id="property-conservative"></a> `conservative()` | () => [`RetryConfig`](Interface.RetryConfig.md) | Conservative retry: few retries, long delays | rate-limit/retry.ts:230 |
| <a id="property-none"></a> `none()` | () => [`RetryConfig`](Interface.RetryConfig.md) | No retry: fail immediately | rate-limit/retry.ts:252 |
| <a id="property-respectful"></a> `respectful()` | () => [`RetryConfig`](Interface.RetryConfig.md) | Respect API limits: use Retry-After headers when available | rate-limit/retry.ts:259 |
