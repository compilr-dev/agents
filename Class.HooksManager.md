---
title: "HooksManager"
parent: Classes
nav_order: 1
---


# Class: HooksManager

Defined in: hooks/manager.ts:53

Manages lifecycle hooks for agent customization

## Constructors

### Constructor

```ts
new HooksManager(options?): HooksManager;
```

Defined in: hooks/manager.ts:65

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `options` | [`HooksManagerOptions`](Interface.HooksManagerOptions.md) |

#### Returns

`HooksManager`

## Methods

### clear()

```ts
clear(): void;
```

Defined in: hooks/manager.ts:295

Clear all hooks

#### Returns

`void`

### getHookCounts()

```ts
getHookCounts(): Record<keyof HooksConfig, number>;
```

Defined in: hooks/manager.ts:664

Get hook counts by type

#### Returns

`Record`\<keyof [`HooksConfig`](Interface.HooksConfig.md), `number`\>

### getHookIds()

```ts
getHookIds(): string[];
```

Defined in: hooks/manager.ts:679

Get all registered hook IDs

#### Returns

`string`[]

### hasHooks()

```ts
hasHooks(): boolean;
```

Defined in: hooks/manager.ts:649

Check if any hooks are registered

#### Returns

`boolean`

### registerAfterIteration()

```ts
registerAfterIteration(hook, options?): string;
```

Defined in: hooks/manager.ts:143

Register an after:iteration hook

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `hook` | [`AfterIterationHook`](TypeAlias.AfterIterationHook.md) |
| `options?` | [`HookRegistrationOptions`](Interface.HookRegistrationOptions.md) |

#### Returns

`string`

### registerAfterLLM()

```ts
registerAfterLLM(hook, options?): string;
```

Defined in: hooks/manager.ts:185

Register an after:llm hook

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `hook` | [`AfterLLMHook`](TypeAlias.AfterLLMHook.md) |
| `options?` | [`HookRegistrationOptions`](Interface.HookRegistrationOptions.md) |

#### Returns

`string`

### registerAfterTool()

```ts
registerAfterTool(hook, options?): string;
```

Defined in: hooks/manager.ts:227

Register an after:tool hook

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `hook` | [`AfterToolHook`](TypeAlias.AfterToolHook.md) |
| `options?` | [`HookRegistrationOptions`](Interface.HookRegistrationOptions.md) |

#### Returns

`string`

### registerBeforeIteration()

```ts
registerBeforeIteration(hook, options?): string;
```

Defined in: hooks/manager.ts:122

Register a before:iteration hook

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `hook` | [`BeforeIterationHook`](TypeAlias.BeforeIterationHook.md) |
| `options?` | [`HookRegistrationOptions`](Interface.HookRegistrationOptions.md) |

#### Returns

`string`

### registerBeforeLLM()

```ts
registerBeforeLLM(hook, options?): string;
```

Defined in: hooks/manager.ts:164

Register a before:llm hook

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `hook` | [`BeforeLLMHook`](TypeAlias.BeforeLLMHook.md) |
| `options?` | [`HookRegistrationOptions`](Interface.HookRegistrationOptions.md) |

#### Returns

`string`

### registerBeforeTool()

```ts
registerBeforeTool(hook, options?): string;
```

Defined in: hooks/manager.ts:206

Register a before:tool hook

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `hook` | [`BeforeToolHook`](TypeAlias.BeforeToolHook.md) |
| `options?` | [`HookRegistrationOptions`](Interface.HookRegistrationOptions.md) |

#### Returns

`string`

### registerFromConfig()

```ts
registerFromConfig(config): void;
```

Defined in: hooks/manager.ts:81

Register hooks from a configuration object

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `config` | [`HooksConfig`](Interface.HooksConfig.md) |

#### Returns

`void`

### registerOnError()

```ts
registerOnError(hook, options?): string;
```

Defined in: hooks/manager.ts:248

Register an onError hook

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `hook` | [`OnErrorHook`](TypeAlias.OnErrorHook.md) |
| `options?` | [`HookRegistrationOptions`](Interface.HookRegistrationOptions.md) |

#### Returns

`string`

### runAfterIteration()

```ts
runAfterIteration(context): Promise<void>;
```

Defined in: hooks/manager.ts:355

Run after:iteration hooks

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `context` | [`IterationHookContext`](Interface.IterationHookContext.md) & \{ `completedWithText`: `boolean`; `toolCalls`: \{ `input`: `Record`\<`string`, `unknown`\>; `name`: `string`; `result`: [`ToolExecutionResult`](Interface.ToolExecutionResult.md); \}[]; \} |

#### Returns

`Promise`\<`void`\>

### runAfterLLM()

```ts
runAfterLLM(context): Promise<void>;
```

Defined in: hooks/manager.ts:451

Run after:llm hooks

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `context` | [`AfterLLMHookContext`](Interface.AfterLLMHookContext.md) |

#### Returns

`Promise`\<`void`\>

### runAfterTool()

```ts
runAfterTool(context): Promise<ToolExecutionResult>;
```

Defined in: hooks/manager.ts:545

Run after:tool hooks

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `context` | [`AfterToolHookContext`](Interface.AfterToolHookContext.md) |

#### Returns

`Promise`\<[`ToolExecutionResult`](Interface.ToolExecutionResult.md)\>

potentially modified result

### runBeforeIteration()

```ts
runBeforeIteration(context): Promise<boolean>;
```

Defined in: hooks/manager.ts:314

Run before:iteration hooks

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `context` | [`IterationHookContext`](Interface.IterationHookContext.md) |

#### Returns

`Promise`\<`boolean`\>

true to continue, false to skip iteration

### runBeforeLLM()

```ts
runBeforeLLM(context): Promise<{
  messages: Message[];
  systemPrompt: string;
  tools: ToolDefinition[];
}>;
```

Defined in: hooks/manager.ts:401

Run before:llm hooks

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `context` | [`LLMHookContext`](Interface.LLMHookContext.md) |

#### Returns

`Promise`\<\{
  `messages`: [`Message`](Interface.Message.md)[];
  `systemPrompt`: `string`;
  `tools`: `ToolDefinition`[];
\}\>

potentially modified messages and tools

### runBeforeTool()

```ts
runBeforeTool(context): Promise<{
  input: Record<string, unknown>;
  proceed: boolean;
  skipResult?: ToolExecutionResult;
}>;
```

Defined in: hooks/manager.ts:488

Run before:tool hooks

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `context` | [`ToolHookContext`](Interface.ToolHookContext.md) |

#### Returns

`Promise`\<\{
  `input`: `Record`\<`string`, `unknown`\>;
  `proceed`: `boolean`;
  `skipResult?`: [`ToolExecutionResult`](Interface.ToolExecutionResult.md);
\}\>

whether to proceed and potentially modified input or skip result

### runOnError()

```ts
runOnError(context): Promise<ErrorHookResult>;
```

Defined in: hooks/manager.ts:591

Run onError hooks

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `context` | [`ErrorHookContext`](Interface.ErrorHookContext.md) |

#### Returns

`Promise`\<[`ErrorHookResult`](Interface.ErrorHookResult.md)\>

error handling result

### unregister()

```ts
unregister(hookId): boolean;
```

Defined in: hooks/manager.ts:269

Unregister a hook by ID

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `hookId` | `string` |

#### Returns

`boolean`
