---
title: "AcquireResult"
parent: Interfaces
nav_order: 1
---


# Interface: AcquireResult

Defined in: rate-limit/types.ts:142

Result of acquiring a rate limit token

## Properties

### acquired

```ts
acquired: boolean;
```

Defined in: rate-limit/types.ts:146

Whether the acquisition was successful

### estimatedWaitMs?

```ts
optional estimatedWaitMs?: number;
```

Defined in: rate-limit/types.ts:156

If not acquired, the estimated wait time (ms)

### waitedMs

```ts
waitedMs: number;
```

Defined in: rate-limit/types.ts:151

Time waited to acquire the token (ms)
