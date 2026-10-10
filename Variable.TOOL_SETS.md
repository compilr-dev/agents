---
title: "TOOL_SETS"
parent: Variables
nav_order: 1
---


# Variable: TOOL\_SETS

```ts
const TOOL_SETS: {
  READ_ONLY: readonly ["glob", "grep", "read_file"];
  READ_ONLY_WITH_BASH: readonly ["bash", "glob", "grep", "read_file"];
  READ_ONLY_WITH_WEB: readonly ["web_fetch", "glob", "grep", "read_file"];
  REFACTOR: readonly ["glob", "grep", "read_file", "edit", "write_file"];
  SECURITY_AUDIT: readonly ["glob", "grep", "read_file", "bash"];
};
```

Defined in: tools/builtin/tool-names.ts:36

Common tool sets for agent types
Use these instead of hardcoding tool arrays

## Type Declaration

| Name | Type | Description | Defined in |
| ------ | ------ | ------ | ------ |
| <a id="property-read_only"></a> `READ_ONLY` | readonly \[`"glob"`, `"grep"`, `"read_file"`\] | Read-only tools for exploration and code review | tools/builtin/tool-names.ts:38 |
| <a id="property-read_only_with_bash"></a> `READ_ONLY_WITH_BASH` | readonly \[`"bash"`, `"glob"`, `"grep"`, `"read_file"`\] | Read-only tools plus bash for running commands | tools/builtin/tool-names.ts:41 |
| <a id="property-read_only_with_web"></a> `READ_ONLY_WITH_WEB` | readonly \[`"web_fetch"`, `"glob"`, `"grep"`, `"read_file"`\] | Read-only tools plus web fetch for documentation lookup | tools/builtin/tool-names.ts:44 |
| <a id="property-refactor"></a> `REFACTOR` | readonly \[`"glob"`, `"grep"`, `"read_file"`, `"edit"`, `"write_file"`\] | Tools for refactoring (read + edit + write, no bash) | tools/builtin/tool-names.ts:52 |
| <a id="property-security_audit"></a> `SECURITY_AUDIT` | readonly \[`"glob"`, `"grep"`, `"read_file"`, `"bash"`\] | Tools for security auditing (read + bash for dependency checks) | tools/builtin/tool-names.ts:61 |
