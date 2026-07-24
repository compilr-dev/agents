---
title: "OTelSpan"
parent: Type Aliases
nav_order: 1
---


# Type Alias: OTelSpan

```ts
type OTelSpan = {
  addEvent: void;
  end: void;
  setAttribute: void;
  setStatus: void;
  spanContext: {
     spanId: string;
     traceId: string;
  };
};
```

Defined in: tracing/types.ts:256

## Methods

### addEvent()

```ts
addEvent(name, attributes?): void;
```

Defined in: tracing/types.ts:259

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `name` | `string` |
| `attributes?` | `Record`\<`string`, `unknown`\> |

#### Returns

`void`

### end()

```ts
end(endTime?): void;
```

Defined in: tracing/types.ts:260

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `endTime?` | `number` |

#### Returns

`void`

### setAttribute()

```ts
setAttribute(key, value): void;
```

Defined in: tracing/types.ts:257

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `key` | `string` |
| `value` | [`AttributeValue`](TypeAlias.AttributeValue.md) |

#### Returns

`void`

### setStatus()

```ts
setStatus(status): void;
```

Defined in: tracing/types.ts:258

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `status` | \{ `code`: `number`; `message?`: `string`; \} |
| `status.code` | `number` |
| `status.message?` | `string` |

#### Returns

`void`

### spanContext()

```ts
spanContext(): {
  spanId: string;
  traceId: string;
};
```

Defined in: tracing/types.ts:261

#### Returns

```ts
{
  spanId: string;
  traceId: string;
}
```

| Name | Type | Defined in |
| ------ | ------ | ------ |
| `spanId` | `string` | tracing/types.ts:261 |
| `traceId` | `string` | tracing/types.ts:261 |
