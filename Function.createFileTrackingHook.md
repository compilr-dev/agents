---
title: "createFileTrackingHook"
parent: Functions
nav_order: 1
---


# Function: createFileTrackingHook()

```ts
function createFileTrackingHook(tracker): AfterToolHook;
```

Defined in: context/file-tracking-hook.ts:79

Create an afterTool hook that tracks file accesses

## Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `tracker` | [`FileAccessTracker`](Class.FileAccessTracker.md) | FileAccessTracker instance to record accesses |

## Returns

[`AfterToolHook`](TypeAlias.AfterToolHook.md)

An afterTool hook function
