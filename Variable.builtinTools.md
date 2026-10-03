---
title: "builtinTools"
parent: Variables
nav_order: 1
---


# Variable: builtinTools

```ts
const builtinTools: {
  askUser: Tool<AskUserInput>;
  askUserSimple: Tool<AskUserSimpleInput>;
  backlogRead: Tool<BacklogReadInput>;
  backlogWrite: Tool<BacklogWriteInput>;
  bash: Tool<BashInput>;
  bashOutput: Tool<BashOutputInput>;
  edit: Tool<EditInput>;
  glob: Tool<GlobInput>;
  grep: Tool<GrepInput>;
  killShell: Tool<KillShellInput>;
  readFile: Tool<ReadFileInput>;
  suggest: Tool<SuggestInput>;
  todoRead: Tool<TodoReadInput>;
  todoWrite: Tool<TodoWriteInput>;
  webFetch: Tool<WebFetchInput>;
  writeFile: Tool<WriteFileInput>;
};
```

Defined in: tools/builtin/index.ts:145

## Type Declaration

| Name | Type | Default value | Defined in |
| ------ | ------ | ------ | ------ |
| <a id="property-askuser"></a> `askUser` | [`Tool`](Interface.Tool.md)\<`AskUserInput`\> | `askUserTool` | tools/builtin/index.ts:158 |
| <a id="property-askusersimple"></a> `askUserSimple` | [`Tool`](Interface.Tool.md)\<`AskUserSimpleInput`\> | `askUserSimpleTool` | tools/builtin/index.ts:159 |
| <a id="property-backlogread"></a> `backlogRead` | [`Tool`](Interface.Tool.md)\<`BacklogReadInput`\> | `backlogReadTool` | tools/builtin/index.ts:160 |
| <a id="property-backlogwrite"></a> `backlogWrite` | [`Tool`](Interface.Tool.md)\<`BacklogWriteInput`\> | `backlogWriteTool` | tools/builtin/index.ts:161 |
| <a id="property-bash"></a> `bash` | [`Tool`](Interface.Tool.md)\<[`BashInput`](Interface.BashInput.md)\> | `bashTool` | tools/builtin/index.ts:148 |
| <a id="property-bashoutput"></a> `bashOutput` | [`Tool`](Interface.Tool.md)\<`BashOutputInput`\> | `bashOutputTool` | tools/builtin/index.ts:149 |
| <a id="property-edit"></a> `edit` | [`Tool`](Interface.Tool.md)\<[`EditInput`](Interface.EditInput.md)\> | `editTool` | tools/builtin/index.ts:153 |
| <a id="property-glob"></a> `glob` | [`Tool`](Interface.Tool.md)\<[`GlobInput`](Interface.GlobInput.md)\> | `globTool` | tools/builtin/index.ts:152 |
| <a id="property-grep"></a> `grep` | [`Tool`](Interface.Tool.md)\<[`GrepInput`](Interface.GrepInput.md)\> | `grepTool` | tools/builtin/index.ts:151 |
| <a id="property-killshell"></a> `killShell` | [`Tool`](Interface.Tool.md)\<`KillShellInput`\> | `killShellTool` | tools/builtin/index.ts:150 |
| <a id="property-readfile"></a> `readFile` | [`Tool`](Interface.Tool.md)\<[`ReadFileInput`](Interface.ReadFileInput.md)\> | `readFileTool` | tools/builtin/index.ts:146 |
| <a id="property-suggest"></a> `suggest` | [`Tool`](Interface.Tool.md)\<[`SuggestInput`](Interface.SuggestInput.md)\> | `suggestTool` | tools/builtin/index.ts:157 |
| <a id="property-todoread"></a> `todoRead` | [`Tool`](Interface.Tool.md)\<[`TodoReadInput`](Interface.TodoReadInput.md)\> | `todoReadTool` | tools/builtin/index.ts:155 |
| <a id="property-todowrite"></a> `todoWrite` | [`Tool`](Interface.Tool.md)\<[`TodoWriteInput`](Interface.TodoWriteInput.md)\> | `todoWriteTool` | tools/builtin/index.ts:154 |
| <a id="property-webfetch"></a> `webFetch` | [`Tool`](Interface.Tool.md)\<`WebFetchInput`\> | `webFetchTool` | tools/builtin/index.ts:156 |
| <a id="property-writefile"></a> `writeFile` | [`Tool`](Interface.Tool.md)\<[`WriteFileInput`](Interface.WriteFileInput.md)\> | `writeFileTool` | tools/builtin/index.ts:147 |
