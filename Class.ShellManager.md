---
title: "ShellManager"
parent: Classes
nav_order: 1
---


# Class: ShellManager

Defined in: tools/builtin/shell-manager.ts:138

Manages background shell processes

## Constructors

### Constructor

```ts
new ShellManager(options?): ShellManager;
```

Defined in: tools/builtin/shell-manager.ts:146

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `options?` | `ShellManagerOptions` |

#### Returns

`ShellManager`

## Methods

### adoptProcess()

```ts
adoptProcess(process, options): string;
```

Defined in: tools/builtin/shell-manager.ts:455

Adopt an existing running process into the shell manager.
Used when moving a foreground bash command to background (Ctrl+B).

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `process` | `ChildProcess` | The ChildProcess to adopt |
| `options` | \{ `command`: `string`; `cwd?`: `string`; `initialStderr?`: `string`; `initialStdout?`: `string`; \} | Options including command and initial buffers |
| `options.command` | `string` | - |
| `options.cwd?` | `string` | - |
| `options.initialStderr?` | `string` | - |
| `options.initialStdout?` | `string` | - |

#### Returns

`string`

The shell ID for tracking

### clearCompleted()

```ts
clearCompleted(): number;
```

Defined in: tools/builtin/shell-manager.ts:422

Clear all completed/failed/killed shells

#### Returns

`number`

### dispose()

```ts
dispose(): void;
```

Defined in: tools/builtin/shell-manager.ts:516

Cleanup - kill all shells and clear state

#### Returns

`void`

### get()

```ts
get(id): BackgroundShell | null;
```

Defined in: tools/builtin/shell-manager.ts:395

Get shell info

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |

#### Returns

`BackgroundShell` \| `null`

### getAllOutput()

```ts
getAllOutput(id): ShellOutput | null;
```

Defined in: tools/builtin/shell-manager.ts:273

Get all output from a shell (including previously read)

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |

#### Returns

`ShellOutput` \| `null`

### getOutput()

```ts
getOutput(id, filter?): ShellOutput | null;
```

Defined in: tools/builtin/shell-manager.ts:231

Get output from a shell (only new output since last read)

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |
| `filter?` | `RegExp` |

#### Returns

`ShellOutput` \| `null`

### kill()

```ts
kill(id): boolean;
```

Defined in: tools/builtin/shell-manager.ts:292

Kill a background shell

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |

#### Returns

`boolean`

### killAll()

```ts
killAll(): number;
```

Defined in: tools/builtin/shell-manager.ts:436

Kill all running shells

#### Returns

`number`

### list()

```ts
list(): BackgroundShell[];
```

Defined in: tools/builtin/shell-manager.ts:381

List all shells

#### Returns

`BackgroundShell`[]

### listRunning()

```ts
listRunning(): BackgroundShell[];
```

Defined in: tools/builtin/shell-manager.ts:388

List running shells only

#### Returns

`BackgroundShell`[]

### remove()

```ts
remove(id): boolean;
```

Defined in: tools/builtin/shell-manager.ts:403

Remove a shell from tracking (only if not running)

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |

#### Returns

`boolean`

### spawn()

```ts
spawn(command, options?): string;
```

Defined in: tools/builtin/shell-manager.ts:156

Spawn a new background shell

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `command` | `string` |
| `options?` | \{ `cwd?`: `string`; `env?`: `Record`\<`string`, `string`\>; \} |
| `options.cwd?` | `string` |
| `options.env?` | `Record`\<`string`, `string`\> |

#### Returns

`string`

### verifyAllStatus()

```ts
verifyAllStatus(): number;
```

Defined in: tools/builtin/shell-manager.ts:365

Verify all shells and sync their status.
Returns number of shells whose status was corrected.

#### Returns

`number`

### verifyStatus()

```ts
verifyStatus(id): ShellStatus | null;
```

Defined in: tools/builtin/shell-manager.ts:338

Verify and sync shell status with actual process state.
Call this to ensure status reflects reality after potential race conditions.

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |

#### Returns

`ShellStatus` \| `null`
