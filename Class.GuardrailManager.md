---
title: "GuardrailManager"
parent: Classes
nav_order: 1
---


# Class: GuardrailManager

Defined in: guardrails/manager.ts:58

GuardrailManager - Manages pattern-based safety checks for tool execution

## Example

```typescript
const manager = new GuardrailManager({
  enabled: true,
  includeDefaults: true,
  custom: [
    {
      id: 'no-prod-db',
      name: 'Production Database Protection',
      description: 'Prevent operations on production database',
      patterns: [/prod.*db/i, /production.*database/i],
      action: 'block',
      message: 'Operations on production database are blocked',
    }
  ],
  onTriggered: async (result, context) => {
    if (result.action === 'confirm') {
      return await askUserConfirmation(result.guardrail.message);
    }
    return result.action !== 'block';
  }
});

// Check before tool execution
const result = manager.check('bash', { command: 'rm -rf /' });
if (result.triggered && result.action === 'block') {
  throw new Error(result.guardrail.message);
}
```

## Constructors

### Constructor

```ts
new GuardrailManager(options?): GuardrailManager;
```

Defined in: guardrails/manager.ts:65

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `options` | [`GuardrailManagerOptions`](Interface.GuardrailManagerOptions.md) |

#### Returns

`GuardrailManager`

## Accessors

### enabled

#### Get Signature

```ts
get enabled(): boolean;
```

Defined in: guardrails/manager.ts:176

Check if guardrails are enabled

##### Returns

`boolean`

### size

#### Get Signature

```ts
get size(): number;
```

Defined in: guardrails/manager.ts:169

Get the number of guardrails

##### Returns

`number`

## Methods

### add()

```ts
add(input): Guardrail;
```

Defined in: guardrails/manager.ts:96

Add a custom guardrail

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `input` | [`GuardrailInput`](Interface.GuardrailInput.md) |

#### Returns

[`Guardrail`](Interface.Guardrail.md)

### check()

```ts
check(toolName, input): GuardrailResult;
```

Defined in: guardrails/manager.ts:197

Check tool input against all applicable guardrails

For inputs with a `command` field (e.g. bash tool), automatically
parses compound commands and checks each subcommand independently.

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `toolName` | `string` | Name of the tool being called |
| `input` | `unknown` | Tool input to check |

#### Returns

[`GuardrailResult`](Interface.GuardrailResult.md)

GuardrailResult indicating if any guardrail was triggered

### checkAndHandle()

```ts
checkAndHandle(toolName, input): Promise<{
  proceed: boolean;
  result: GuardrailResult;
}>;
```

Defined in: guardrails/manager.ts:310

Check and handle guardrail triggering

This method checks the input and calls the onTriggered handler if configured.
Returns true if execution should proceed, false if blocked.

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `toolName` | `string` | Name of the tool being called |
| `input` | `unknown` | Tool input to check |

#### Returns

`Promise`\<\{
  `proceed`: `boolean`;
  `result`: [`GuardrailResult`](Interface.GuardrailResult.md);
\}\>

Promise<{ proceed: boolean; result: GuardrailResult }>

### checkCommand()

```ts
checkCommand(
   toolName, 
   command, 
   originalInput?): GuardrailResult;
```

Defined in: guardrails/manager.ts:229

Check a compound shell command against guardrails.

Parses the command into subcommands (splitting on |, &&, ||, ;)
and validates each independently. Also checks the full command string
to catch cross-subcommand patterns (e.g. `curl ... | bash`).
Returns the highest-severity match with subcommand context.

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `toolName` | `string` | Name of the tool being called |
| `command` | `string` | The shell command string |
| `originalInput?` | `unknown` | The original tool input (for result metadata) |

#### Returns

[`GuardrailResult`](Interface.GuardrailResult.md)

GuardrailResult indicating if any guardrail was triggered

### disable()

```ts
disable(id): boolean;
```

Defined in: guardrails/manager.ts:159

Disable a guardrail

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |

#### Returns

`boolean`

### enable()

```ts
enable(id): boolean;
```

Defined in: guardrails/manager.ts:149

Enable a guardrail

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |

#### Returns

`boolean`

### get()

```ts
get(id): Guardrail | undefined;
```

Defined in: guardrails/manager.ts:109

Get a guardrail by ID

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |

#### Returns

[`Guardrail`](Interface.Guardrail.md) \| `undefined`

### getAll()

```ts
getAll(): Guardrail[];
```

Defined in: guardrails/manager.ts:116

Get all guardrails

#### Returns

[`Guardrail`](Interface.Guardrail.md)[]

### getForTool()

```ts
getForTool(toolName): Guardrail[];
```

Defined in: guardrails/manager.ts:123

Get guardrails that apply to a specific tool

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `toolName` | `string` |

#### Returns

[`Guardrail`](Interface.Guardrail.md)[]

### has()

```ts
has(id): boolean;
```

Defined in: guardrails/manager.ts:135

Check if a guardrail exists

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |

#### Returns

`boolean`

### onEvent()

```ts
onEvent(handler): void;
```

Defined in: guardrails/manager.ts:89

Set the event handler for guardrail events

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `handler` | [`GuardrailEventHandler`](TypeAlias.GuardrailEventHandler.md) |

#### Returns

`void`

### remove()

```ts
remove(id): boolean;
```

Defined in: guardrails/manager.ts:142

Remove a guardrail by ID

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `id` | `string` |

#### Returns

`boolean`

### setEnabled()

```ts
setEnabled(enabled): void;
```

Defined in: guardrails/manager.ts:183

Enable or disable all guardrails

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `enabled` | `boolean` |

#### Returns

`void`
