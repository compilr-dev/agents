---
title: "PruneConfig"
parent: Interfaces
nav_order: 1
---


# Interface: PruneConfig

Defined in: context/dead-message-pruner.ts:19

## Properties

### permissionExchanges

```ts
permissionExchanges: boolean;
```

Defined in: context/dead-message-pruner.ts:23

Enable permission exchange pruning (default: true)

### permissionTools

```ts
permissionTools: string[];
```

Defined in: context/dead-message-pruner.ts:25

Tool names considered permission exchanges

### protectedTurns

```ts
protectedTurns: number;
```

Defined in: context/dead-message-pruner.ts:27

Never prune messages newer than this many turns (default: 4)

### supersededErrors

```ts
supersededErrors: boolean;
```

Defined in: context/dead-message-pruner.ts:21

Enable superseded error pruning (default: true)
