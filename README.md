# @compilr-dev/agents

> Lightweight multi-LLM agent library for building CLI AI assistants

[![npm version](https://img.shields.io/npm/v/@compilr-dev/agents.svg)](https://www.npmjs.com/package/@compilr-dev/agents)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Features

- **Multi-LLM Support** - Claude, OpenAI GPT-4, Google Gemini, Ollama (local)
- **Built-in Tools** - 13 tools for file ops, search, bash, and more
- **Sub-agents** - Spawn specialized agents for complex tasks
- **Context Management** - Token budgeting, compaction, summarization
- **Skills System** - 11 reusable prompts for common workflows
- **Safety Features** - Permissions, guardrails, anchors, rehearsal mode
- **Streaming** - Real-time event streaming with abort support
- **MCP Integration** - Load tools from MCP servers

## Quick Start

```bash
npm install @compilr-dev/agents
```

```typescript
import { Agent, ClaudeProvider } from '@compilr-dev/agents';

const agent = new Agent({
  provider: new ClaudeProvider({ apiKey: process.env.ANTHROPIC_API_KEY }),
  systemPrompt: 'You are a helpful assistant.',
});

for await (const event of agent.run('Hello!')) {
  if (event.type === 'text') {
    process.stdout.write(event.content);
  }
}
```

## LLM Providers

```typescript
import {
  ClaudeProvider,
  OpenAIProvider,
  GeminiProvider,
  OllamaProvider
} from '@compilr-dev/agents';

// Claude (Anthropic)
new ClaudeProvider({ apiKey: 'sk-ant-...' });

// OpenAI GPT-4
new OpenAIProvider({ apiKey: 'sk-...' });

// Google Gemini
new GeminiProvider({ apiKey: '...' });

// Ollama (local)
new OllamaProvider({ model: 'llama3' });
```

## Built-in Tools

| Tool | Description |
|------|-------------|
| `readFile` | Read file contents |
| `writeFile` | Write to files |
| `edit` | Edit files with search/replace |
| `bash` | Execute shell commands |
| `bashOutput` | Get output from background shell |
| `killShell` | Terminate background shell |
| `grep` | Search file contents |
| `glob` | Find files by pattern |
| `todoWrite` | Manage task list |
| `todoRead` | Read task list |
| `webFetch` | Fetch URL content |
| `task` | Spawn sub-agents |
| `suggest` | Get action suggestions |

## Sub-agents (Task Tool)

Spawn specialized agents for complex tasks:

```typescript
import { createTaskTool } from '@compilr-dev/agents';

const taskTool = createTaskTool({
  provider,
  agentTypes: {
    explore: { description: 'Explore codebase', systemPrompt: '...' },
    'code-review': { description: 'Review code', systemPrompt: '...' },
    plan: { description: 'Create plans', systemPrompt: '...' },
  },
});
```

**Built-in agent types:** explore, code-review, general, plan, test-runner, doc-lookup, refactor, security-audit, debug

## Context Management

Manage token budgets and prevent context overflow:

```typescript
import { ContextManager } from '@compilr-dev/agents';

const contextManager = new ContextManager({
  maxTokens: 100000,
  budgets: {
    system: 0.15,
    anchors: 0.10,
    conversation: 0.75,
  },
});
```

## Skills

Reusable prompts for common workflows:

```typescript
import { SkillRegistry, defaultSkills } from '@compilr-dev/agents';

const skills = new SkillRegistry();
defaultSkills.forEach(skill => skills.register(skill));

const prompt = skills.invoke('code-review', { focus: 'security' });
```

**Built-in skills:** code-review, debug, explain, refactor, planning, security-review, design, refine, sketch, build, scaffold

## Safety Features

### Permissions

```typescript
import { PermissionManager } from '@compilr-dev/agents';

const permissions = new PermissionManager();
permissions.setPermission('bash', 'once'); // Ask each time
permissions.setPermission('writeFile', 'session'); // Ask once per session
```

### Guardrails

```typescript
import { defaultGuardrails } from '@compilr-dev/agents';
// 15 built-in patterns for secrets, PII, dangerous commands, etc.
```

### Anchors

```typescript
import { AnchorManager } from '@compilr-dev/agents';
// Keep critical information across context compaction
```

## Requirements

- **Node.js** 18 or higher
- **API Key** for your chosen provider (except Ollama)

## Peer Dependencies

- `@anthropic-ai/sdk` (optional, for Claude)
- `@modelcontextprotocol/sdk` (optional, for MCP)

## Links

- [Website](https://compilr.dev)
- [Documentation](https://compilr.dev/docs)
- [npm Package](https://www.npmjs.com/package/@compilr-dev/agents)
- [GitHub Issues](https://github.com/compilr-dev/agents/issues)

## Related Packages

- [@compilr-dev/cli](https://www.npmjs.com/package/@compilr-dev/cli) - AI-powered CLI assistant
- [@compilr-dev/agents-coding](https://www.npmjs.com/package/@compilr-dev/agents-coding) - Coding-specific tools

## License

MIT - See [LICENSE](LICENSE) for details.

---

<p align="center">
  <strong>Built with care by <a href="https://compilr.dev">compilr.dev</a></strong>
</p>
