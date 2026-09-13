---
title: "execStream"
parent: Functions
nav_order: 1
---


# Function: execStream()

```ts
function execStream(command, options?): {
  promise: Promise<number>;
  stderr: AsyncIterable<string>;
  stdout: AsyncIterable<string>;
};
```

Defined in: tools/builtin/bash.ts:857

Execute a command with streaming output (for long-running commands)

Note: This is a lower-level function for cases where you need
to stream output as it arrives.

## Parameters

| Parameter | Type |
| ------ | ------ |
| `command` | `string` |
| `options?` | \{ `cwd?`: `string`; `env?`: `Record`\<`string`, `string`\>; `shell?`: `string`; \} |
| `options.cwd?` | `string` |
| `options.env?` | `Record`\<`string`, `string`\> |
| `options.shell?` | `string` |

## Returns

```ts
{
  promise: Promise<number>;
  stderr: AsyncIterable<string>;
  stdout: AsyncIterable<string>;
}
```

| Name | Type | Defined in |
| ------ | ------ | ------ |
| `promise` | `Promise`\<`number`\> | tools/builtin/bash.ts:867 |
| `stderr` | `AsyncIterable`\<`string`\> | tools/builtin/bash.ts:866 |
| `stdout` | `AsyncIterable`\<`string`\> | tools/builtin/bash.ts:865 |
