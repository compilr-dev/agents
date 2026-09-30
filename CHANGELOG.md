# Changelog

All notable changes to this package are documented here.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project follows [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

> **Beta notice:** versions in the `0.x` range may contain breaking changes
> between minors. Read each release entry before upgrading.

---

## [Unreleased]

### Added

- **OpenAI Responses API transport** (`OpenAIResponsesProvider`, `/v1/responses`). Every current
  OpenAI model (`gpt-6-*`, `gpt-5.6-*`) refuses function tools on `/v1/chat/completions`, with or
  without `reasoning_effort`, so this is the only endpoint on which the OpenAI provider can call
  tools at all. Streams text, tool calls and reasoning boundaries; maps `ThinkingConfig` to
  `reasoning.effort`; reads the `input_tokens` / `output_tokens` usage shape including cached and
  reasoning tokens.
- **Per-model routing** (`parseOpenAIModel`, `routeFor`, `allowedEfforts`, `clampEffort`). Matched
  by generation, not by a list of names: `gpt-7-*` and `gpt-6.2-*` will route correctly with no
  code change. A non-`api.openai.com` base URL always stays on Chat Completions, so a `custom` or
  local endpoint is never sent `/v1/responses`.
- `'xhigh'` on `ThinkingConfig.effort`, for the GPT-6 line. Clamped to `'high'` for Claude, which
  has never been sent one.

### Changed

- `OpenAIProvider` is now a **router**: it picks `/v1/responses` or `/v1/chat/completions` per
  call from the model id. Its exported name, factory and config are unchanged, and `name` stays
  `'openai'` on every transport. The previous Chat-Completions class is still available as
  `OpenAIChatCompletionsProvider`.
- The OpenAI default model is now `gpt-6-sol` (was `gpt-4o`, two generations stale).
- A `thinking` config is now honoured for OpenAI models on the Responses transport, where it was
  previously ignored for all non-Claude providers.

### Fixed

- **Chat Completions could not complete a single message on any `gpt-5` model.** They return
  `400 "Unsupported parameter: 'max_tokens' … Use 'max_completion_tokens' instead"`. The OpenAI
  transport now sends `max_completion_tokens` for `gpt-5` and later on the official host, and
  keeps `max_tokens` for `gpt-4*`, custom base URLs and unrecognised ids.

---

For full git history see the repository commit log. Older `0.x` entries will be
backfilled here over time.
