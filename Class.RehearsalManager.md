---
title: "RehearsalManager"
parent: Classes
nav_order: 1
---


# Class: RehearsalManager

Defined in: rehearsal/manager.ts:59

RehearsalManager - Coordinates impact analysis for destructive operations

## Example

```typescript
const manager = new RehearsalManager({
  workingDirectory: '/path/to/project',
});

// Analyze before executing
const result = await manager.rehearse('rm -rf node_modules');

if (result.recommendation === 'abort') {
  console.log('Operation too dangerous:', result.warnings);
} else if (result.recommendation === 'confirm') {
  const confirmed = await askUser(result.impact.summary);
  if (confirmed) {
    // Execute the operation
  }
}
```

## Constructors

### Constructor

```ts
new RehearsalManager(options?): RehearsalManager;
```

Defined in: rehearsal/manager.ts:68

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `options` | [`RehearsalManagerOptions`](Interface.RehearsalManagerOptions.md) |

#### Returns

`RehearsalManager`

## Methods

### findAnalyzer()

```ts
findAnalyzer(operation): RehearsalAnalyzer | undefined;
```

Defined in: rehearsal/manager.ts:168

Find the appropriate analyzer for an operation

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `operation` | `string` |

#### Returns

[`RehearsalAnalyzer`](Interface.RehearsalAnalyzer.md) \| `undefined`

### formatResult()

```ts
formatResult(result): string;
```

Defined in: rehearsal/manager.ts:270

Get a formatted summary of a rehearsal result

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `result` | [`RehearsalResult`](Interface.RehearsalResult.md) |

#### Returns

`string`

### getAnalyzers()

```ts
getAnalyzers(): RehearsalAnalyzer[];
```

Defined in: rehearsal/manager.ts:116

Get all registered analyzers

#### Returns

[`RehearsalAnalyzer`](Interface.RehearsalAnalyzer.md)[]

### getSessionModifiedFiles()

```ts
getSessionModifiedFiles(): string[];
```

Defined in: rehearsal/manager.ts:149

Get files modified in this session

#### Returns

`string`[]

### isDestructive()

```ts
isDestructive(operation): boolean;
```

Defined in: rehearsal/manager.ts:156

Check if an operation is potentially destructive

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `operation` | `string` |

#### Returns

`boolean`

### onEvent()

```ts
onEvent(handler): this;
```

Defined in: rehearsal/manager.ts:123

Set event handler

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `handler` | [`RehearsalEventHandler`](TypeAlias.RehearsalEventHandler.md) |

#### Returns

`this`

### registerAnalyzer()

```ts
registerAnalyzer(analyzer): this;
```

Defined in: rehearsal/manager.ts:101

Register an analyzer

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `analyzer` | [`RehearsalAnalyzer`](Interface.RehearsalAnalyzer.md) |

#### Returns

`this`

### rehearse()

```ts
rehearse(operation): Promise<RehearsalResult>;
```

Defined in: rehearsal/manager.ts:183

Rehearse an operation - analyze its impact before execution

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `operation` | `string` | The command or operation to analyze |

#### Returns

`Promise`\<[`RehearsalResult`](Interface.RehearsalResult.md)\>

Impact analysis result

### rehearseAll()

```ts
rehearseAll(operations): Promise<RehearsalResult[]>;
```

Defined in: rehearsal/manager.ts:246

Rehearse multiple operations

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `operations` | `string`[] |

#### Returns

`Promise`\<[`RehearsalResult`](Interface.RehearsalResult.md)[]\>

### shouldProceed()

```ts
shouldProceed(operation): Promise<boolean>;
```

Defined in: rehearsal/manager.ts:262

Check if an operation should proceed based on rehearsal

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `operation` | `string` |

#### Returns

`Promise`\<`boolean`\>

true if safe to proceed, false if should abort

### trackFileModification()

```ts
trackFileModification(filePath): void;
```

Defined in: rehearsal/manager.ts:140

Track a file as modified in this session

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `filePath` | `string` |

#### Returns

`void`

### unregisterAnalyzer()

```ts
unregisterAnalyzer(id): boolean;
```

Defined in: rehearsal/manager.ts:109

Unregister an analyzer

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |

#### Returns

`boolean`
