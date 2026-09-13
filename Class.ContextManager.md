---
title: "ContextManager"
parent: Classes
nav_order: 1
---


# Class: ContextManager

Defined in: context/manager.ts:143

Manages the agent's context window — tracks token usage, triggers
compaction when the conversation grows too large, and ensures the
agent never exceeds the model's context limit.

The context window is divided into budgets:
- **System prompt** (~15%) — always present, never compacted
- **Anchors/pins** (~10%) — critical info that survives compaction
- **Conversation history** (~75%) — compacted when budget exceeded

When conversation history exceeds its budget, the manager triggers
smart windowing (3-zone compaction): recent messages preserved,
middle messages summarized, old messages dropped.

## Example

```typescript
const agent = new Agent({
  provider,
  contextManager: new ContextManager({
    maxTokens: 100000,
    budgets: { system: 0.15, anchors: 0.10, conversation: 0.75 },
  }),
});
```

## Constructors

### Constructor

```ts
new ContextManager(options): ContextManager;
```

Defined in: context/manager.ts:163

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `options` | [`ContextManagerOptions`](Interface.ContextManagerOptions.md) |

#### Returns

`ContextManager`

## Methods

### addToCategory()

```ts
addToCategory(category, tokens): void;
```

Defined in: context/manager.ts:410

Add tokens to a category

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `category` | [`ContextCategory`](TypeAlias.ContextCategory.md) |
| `tokens` | `number` |

#### Returns

`void`

### canAddContent()

```ts
canAddContent(estimatedTokens, category): PreflightResult;
```

Defined in: context/manager.ts:873

Check if content can be added to a category

Returns a pre-flight result with recommendations for action.

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `estimatedTokens` | `number` |
| `category` | [`ContextCategory`](TypeAlias.ContextCategory.md) |

#### Returns

[`PreflightResult`](Interface.PreflightResult.md)

### categorizeMessages()

```ts
categorizeMessages(messages, preserveRecentTurns?): Promise<CategorizedMessages>;
```

Defined in: context/manager.ts:549

Categorize all messages by type for smart compaction

This method:
1. Identifies system messages
2. Separates recent messages (last N turns) that should never be compacted
3. Identifies tool results in older messages
4. Classifies remaining older messages as history

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `messages` | [`Message`](Interface.Message.md)[] | All messages to categorize |
| `preserveRecentTurns?` | `number` | Number of recent turns to preserve (default: config value) |

#### Returns

`Promise`\<`CategorizedMessages`\>

### categoryNeedsCompaction()

```ts
categoryNeedsCompaction(category): boolean;
```

Defined in: context/manager.ts:418

Check if a specific category needs compaction

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `category` | [`ContextCategory`](TypeAlias.ContextCategory.md) |

#### Returns

`boolean`

### checkAndWarn()

```ts
checkAndWarn(): void;
```

Defined in: context/manager.ts:1301

Check context and emit warning if needed

#### Returns

`void`

### compact()

```ts
compact(messages, saveToFile): Promise<{
  messages: Message[];
  result: CompactionResult;
}>;
```

Defined in: context/manager.ts:1054

Compact old messages by replacing large content with file references

This is a placeholder - actual implementation requires file system access
which will be provided by the Agent or CLI layer.

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `messages` | [`Message`](Interface.Message.md)[] |
| `saveToFile` | (`content`, `index`) => `Promise`\<`string`\> |

#### Returns

`Promise`\<\{
  `messages`: [`Message`](Interface.Message.md)[];
  `result`: [`CompactionResult`](Interface.CompactionResult.md);
\}\>

### compactCategory()

```ts
compactCategory(
   messages, 
   category, 
   saveToFile): Promise<{
  messages: Message[];
  result: CompactionResult;
}>;
```

Defined in: context/manager.ts:429

Compact only a specific category

This is more targeted than full compaction - only affects messages
in the specified category, leaving others untouched.

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `messages` | [`Message`](Interface.Message.md)[] |
| `category` | [`ContextCategory`](TypeAlias.ContextCategory.md) |
| `saveToFile` | (`content`, `index`) => `Promise`\<`string`\> |

#### Returns

`Promise`\<\{
  `messages`: [`Message`](Interface.Message.md)[];
  `result`: [`CompactionResult`](Interface.CompactionResult.md);
\}\>

### countTokens()

```ts
countTokens(messages): Promise<number>;
```

Defined in: context/manager.ts:205

Count tokens in messages using the provider

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `messages` | [`Message`](Interface.Message.md)[] |

#### Returns

`Promise`\<`number`\>

### createRestorationHintMessage()

```ts
createRestorationHintMessage(): Message | undefined;
```

Defined in: context/manager.ts:351

Create a system message with context restoration hints.
Returns undefined if no hints are available.

The caller (Agent) is responsible for injecting this message
after compaction or summarization.

#### Returns

[`Message`](Interface.Message.md) \| `undefined`

### estimateTokens()

```ts
estimateTokens(content): number;
```

Defined in: context/manager.ts:864

Estimate tokens for a string content

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `content` | `string` |

#### Returns

`number`

### filterContent()

```ts
filterContent(content, type): {
  content: string;
  filtered: boolean;
  originalLength: number;
};
```

Defined in: context/manager.ts:987

Filter large content before adding to context

Returns the filtered content and metadata about what was done.
The caller is responsible for saving to file if needed.

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `content` | `string` |
| `type` | `"tool_result"` \| `"error"` \| `"file"` |

#### Returns

```ts
{
  content: string;
  filtered: boolean;
  originalLength: number;
}
```

| Name | Type | Defined in |
| ------ | ------ | ------ |
| `content` | `string` | context/manager.ts:991 |
| `filtered` | `boolean` | context/manager.ts:992 |
| `originalLength` | `number` | context/manager.ts:993 |

### findOverBudgetCategories()

```ts
findOverBudgetCategories(categorized): ContextCategory[];
```

Defined in: context/manager.ts:623

Find which categories are over their budget allocation

#### Parameters

| Parameter | Type | Description |
| ------ | ------ | ------ |
| `categorized` | `CategorizedMessages` | Categorized messages from categorizeMessages() |

#### Returns

[`ContextCategory`](TypeAlias.ContextCategory.md)[]

Array of categories that exceed their budget, sorted by how much they exceed

### formatRestorationHints()

```ts
formatRestorationHints(): string;
```

Defined in: context/manager.ts:334

Format context restoration hints based on current verbosity level.
Returns empty string if no file tracker is configured or no files have been accessed.

#### Returns

`string`

### getAllBudgets()

```ts
getAllBudgets(): Record<ContextCategory, CategoryBudgetInfo>;
```

Defined in: context/manager.ts:389

Get budget information for all categories

#### Returns

`Record`\<[`ContextCategory`](TypeAlias.ContextCategory.md), [`CategoryBudgetInfo`](Interface.CategoryBudgetInfo.md)\>

### getCategoryBudget()

```ts
getCategoryBudget(category): CategoryBudgetInfo;
```

Defined in: context/manager.ts:370

Get budget information for a specific category

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `category` | [`ContextCategory`](TypeAlias.ContextCategory.md) |

#### Returns

[`CategoryBudgetInfo`](Interface.CategoryBudgetInfo.md)

### getConfig()

```ts
getConfig(): ContextConfig;
```

Defined in: context/manager.ts:319

Get the current configuration

#### Returns

[`ContextConfig`](Interface.ContextConfig.md)

### getFileTracker()

```ts
getFileTracker(): FileAccessTracker | undefined;
```

Defined in: context/manager.ts:326

Get the file access tracker (if configured)

#### Returns

[`FileAccessTracker`](Class.FileAccessTracker.md) \| `undefined`

### getMaxTokens()

```ts
getMaxTokens(): number;
```

Defined in: context/manager.ts:239

Get maximum context tokens

#### Returns

`number`

### getStats()

```ts
getStats(messageCount): ContextStats;
```

Defined in: context/manager.ts:304

Get context statistics

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `messageCount` | `number` |

#### Returns

[`ContextStats`](Interface.ContextStats.md)

### getTokenCount()

```ts
getTokenCount(): number;
```

Defined in: context/manager.ts:225

Get current token count (cached)

#### Returns

`number`

### getTurnCount()

```ts
getTurnCount(): number;
```

Defined in: context/manager.ts:253

Get the current turn count

#### Returns

`number`

### getUtilization()

```ts
getUtilization(): number;
```

Defined in: context/manager.ts:232

Get context utilization (0.0 - 1.0)

#### Returns

`number`

### getVerbosityLevel()

```ts
getVerbosityLevel(): VerbosityLevel;
```

Defined in: context/manager.ts:948

Get current verbosity level based on context utilization

Tools should adapt their output based on this level.

#### Returns

[`VerbosityLevel`](TypeAlias.VerbosityLevel.md)

### incrementTurn()

```ts
incrementTurn(): void;
```

Defined in: context/manager.ts:246

Increment turn count (call after each assistant response)

#### Returns

`void`

### isMinimalMode()

```ts
isMinimalMode(): boolean;
```

Defined in: context/manager.ts:966

Check if we're in minimal mode (critical context pressure)

#### Returns

`boolean`

### needsCompaction()

```ts
needsCompaction(): boolean;
```

Defined in: context/manager.ts:272

Check if compaction is needed

#### Returns

`boolean`

### needsEmergencySummarization()

```ts
needsEmergencySummarization(): boolean;
```

Defined in: context/manager.ts:973

Check if emergency summarization is needed

#### Returns

`boolean`

### needsSummarization()

```ts
needsSummarization(): boolean;
```

Defined in: context/manager.ts:290

Check if summarization is needed (more aggressive than compaction)

#### Returns

`boolean`

### reset()

```ts
reset(): void;
```

Defined in: context/manager.ts:1322

Reset context manager state (for new conversations)

#### Returns

`void`

### setTurnCount()

```ts
setTurnCount(count): void;
```

Defined in: context/manager.ts:260

Set the turn count (for restoring from saved state)

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `count` | `number` |

#### Returns

`void`

### shouldFilter()

```ts
shouldFilter(tokenCount): boolean;
```

Defined in: context/manager.ts:297

Check if content should be filtered before adding

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `tokenCount` | `number` |

#### Returns

`boolean`

### smartCompact()

```ts
smartCompact(messages, options): Promise<{
  messages: Message[];
  result: SmartCompactionResult;
}>;
```

Defined in: context/manager.ts:657

Smart compaction that respects category budgets

Strategy:
1. System messages: Never compacted (critical for agent behavior)
2. Recent messages: Never compacted (needed for conversation continuity)
3. Tool results: Save large results to files, replace with references
4. History: Summarize with LLM

The method compacts categories in order of how much they exceed their budget.

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `messages` | [`Message`](Interface.Message.md)[] |
| `options` | `SmartCompactOptions` |

#### Returns

`Promise`\<\{
  `messages`: [`Message`](Interface.Message.md)[];
  `result`: `SmartCompactionResult`;
\}\>

### summarize()

```ts
summarize(messages, generateSummary): Promise<{
  messages: Message[];
  result: SummarizationResult;
}>;
```

Defined in: context/manager.ts:1136

Summarize conversation history

This is a placeholder - actual implementation requires LLM call
which will be orchestrated by the Agent layer.

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `messages` | [`Message`](Interface.Message.md)[] |
| `generateSummary` | (`messages`) => `Promise`\<`string`\> |

#### Returns

`Promise`\<\{
  `messages`: [`Message`](Interface.Message.md)[];
  `result`: [`SummarizationResult`](Interface.SummarizationResult.md);
\}\>

### summarizeWithRetry()

```ts
summarizeWithRetry(
   messages, 
   generateSummary, 
   options?): Promise<{
  messages: Message[];
  result: SummarizationResult;
}>;
```

Defined in: context/manager.ts:1199

Summarize with support for multiple rounds and emergency mode

Will perform multiple summarization rounds if needed to reach target utilization.
Throws ContextOverflowError if unable to reduce context sufficiently.

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `messages` | [`Message`](Interface.Message.md)[] |
| `generateSummary` | (`messages`) => `Promise`\<`string`\> |
| `options?` | \{ `emergency?`: `boolean`; `maxRounds?`: `number`; `targetUtilization?`: `number`; \} |
| `options.emergency?` | `boolean` |
| `options.maxRounds?` | `number` |
| `options.targetUtilization?` | `number` |

#### Returns

`Promise`\<\{
  `messages`: [`Message`](Interface.Message.md)[];
  `result`: [`SummarizationResult`](Interface.SummarizationResult.md);
\}\>

### updateCategoryUsage()

```ts
updateCategoryUsage(category, tokens): void;
```

Defined in: context/manager.ts:401

Update token usage for a category

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `category` | [`ContextCategory`](TypeAlias.ContextCategory.md) |
| `tokens` | `number` |

#### Returns

`void`

### updateTokenCount()

```ts
updateTokenCount(messages): Promise<number>;
```

Defined in: context/manager.ts:217

Update token count for messages

#### Parameters

| Parameter | Type |
| ------ | ------ |
| `messages` | [`Message`](Interface.Message.md)[] |

#### Returns

`Promise`\<`number`\>
