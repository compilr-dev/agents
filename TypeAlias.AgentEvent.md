---
title: "AgentEvent"
parent: Type Aliases
nav_order: 1
---


# Type Alias: AgentEvent

```ts
type AgentEvent = 
  | {
  iteration: number;
  type: "iteration_start";
}
  | {
  type: "llm_start";
}
  | {
  chunk: StreamChunk;
  type: "llm_chunk";
}
  | {
  hasToolUses: boolean;
  text: string;
  type: "llm_end";
}
  | {
  input: Record<string, unknown>;
  name: string;
  toolUseId: string;
  type: "tool_start";
}
  | {
  output: string;
  stream?: "stdout" | "stderr";
  toolName: string;
  toolUseId: string;
  type: "tool_output";
}
  | {
  name: string;
  result: ToolExecutionResult;
  toolUseId: string;
  type: "tool_end";
}
  | {
  iteration: number;
  type: "iteration_end";
}
  | {
  response: string;
  type: "done";
}
  | {
  threshold: number;
  type: "context_warning";
  utilization: number;
}
  | {
  tokensAfter: number;
  tokensBefore: number;
  type: "context_compacted";
}
  | {
  rounds: number;
  tokensAfter: number;
  tokensBefore: number;
  type: "context_summarized";
}
  | {
  type: "context_overflow";
  utilization: number;
}
  | {
  name: string;
  task: string;
  type: "subagent_start";
}
  | {
  name: string;
  result: SubAgentResult;
  type: "subagent_end";
}
  | {
  consecutiveCalls: number;
  toolName: string;
  type: "tool_loop_warning";
}
  | {
  consecutiveCalls: number;
  nudgeCount: number;
  toolName: string;
  type: "tool_loop_nudge";
}
  | {
  reason: "aborted" | "error";
  sessionId: string;
  type: "abort_checkpoint_saved";
}
  | {
  error: string;
  type: "abort_checkpoint_failed";
}
  | {
  data: unknown;
  metadata?: Record<string, unknown>;
  name: string;
  type: "custom";
}
  | {
  anchor: Anchor;
  type: "anchor_added";
}
  | {
  anchorId: string;
  type: "anchor_removed";
}
  | {
  result: GuardrailResult;
  type: "guardrail_triggered";
}
  | {
  message: string;
  result: GuardrailResult;
  type: "guardrail_blocked";
}
  | {
  message: string;
  result: GuardrailResult;
  type: "guardrail_warning";
}
  | {
  level: PermissionLevel;
  toolName: string;
  type: "permission_granted";
}
  | {
  level: PermissionLevel;
  reason?: string;
  toolName: string;
  type: "permission_denied";
}
  | {
  level: PermissionLevel;
  toolName: string;
  type: "permission_asked";
}
  | {
  model: string;
  tokens: TokenUsage;
  type: "usage_recorded";
}
  | {
  status: BudgetStatus;
  threshold: number;
  type: "usage_budget_warning";
}
  | {
  status: BudgetStatus;
  type: "usage_budget_exceeded";
}
  | {
  action: string;
  reason?: string;
  type: "suggest";
}
  | {
  iteration: number;
  maxIterations: number;
  type: "iteration_limit_reached";
}
  | {
  addedIterations: number;
  newMaxIterations: number;
  type: "iteration_limit_extended";
}
  | {
  newModel: string;
  previousModel: string;
  type: "model_changed";
}
  | {
  attempt: number;
  delayMs: number;
  error: string;
  maxAttempts: number;
  provider: string;
  type: "llm_retry";
}
  | {
  attempts: number;
  error: string;
  provider: string;
  type: "llm_retry_exhausted";
}
  | {
  iteration: number;
  type: "text_repetition_detected";
};
```

Defined in: agent.ts:73

Event types emitted during agent execution
