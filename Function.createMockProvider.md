---
title: "createMockProvider"
parent: Functions
nav_order: 1
---


# Function: createMockProvider()

```ts
function createMockProvider(responses?, config?): MockProvider;
```

Defined in: providers/mock.ts:268

Create a MockProvider with initial responses

## Parameters

| Parameter | Type | Default value |
| ------ | ------ | ------ |
| `responses` | (`string` \| [`MockResponse`](Interface.MockResponse.md))[] | `[]` |
| `config?` | [`MockProviderConfig`](Interface.MockProviderConfig.md) | `undefined` |

## Returns

[`MockProvider`](Class.MockProvider.md)
