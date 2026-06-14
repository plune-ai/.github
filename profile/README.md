# Plune

> **Proof for AI products.** AI quality, verified.

Plune is quality infrastructure for teams shipping with LLMs — methodological rigor,
human-in-the-loop, and CI/CD quality gates. Ship AI with confidence.

**Early, but real** — already on npm and running in CI. Open-source.

## Two layers

**Cairn generates** tests across your app's surfaces. **Plune evaluates** LLM behavior
and gates releases in CI. Two separate layers — use either, or both.

### 🧭 Cairn — test generation

An autonomous QA agent that explores your app and leaves a trail of tests.

- Logs in with a saved Playwright session, explores each page (ARIA snapshot + screenshot), and verifies every locator before trusting it.
- Writes methodology-grade test cases (ISO/IEC/IEEE 29119-4), then generates POM-style `@playwright/test`.
- Self-validates, self-repairs (keep-best), and self-improves via Langfuse — optional, so it runs fully offline.
- Decides what to automate (ATC) vs. leave to a human (MTC); modes `design` · `automate` · `explore`; interactive TUI.
- Surfaces today: UI. Next: API, unit, docs.
- `@plune-ai/cairn` · Apache-2.0 · TypeScript · Node 20+ · _formerly Lex-Bot, relicensed GPL-3.0 → Apache-2.0_

### ✅ Plune CLI + Action — eval

Assertion-testing for LLM behavior, with regression gates in CI.

- `@plune-ai/cli` runs an assertion suite against your provider (Anthropic · OpenAI · OpenRouter) and returns a pass/fail report — locally, in CI, or as a regression diff between runs.
- 10 assertion types — from exact-match and `json-schema` to `llm-judge`, semantic-similarity, and RAG metrics (faithfulness, answer-relevance, context-precision).
- Commands: `plune run` · `plune report` · `plune diff` · `plune init`.
- `eval-action` wraps the CLI: on every PR it runs your evals, diffs against the base branch, and leaves one sticky comment (what regressed, what improved) — optionally blocking merge on a pass→fail regression.
- `@plune-ai/cli` · MIT  ·  `eval-action` · MIT

## Roadmap

- [x] **v0.1** — CLI with assertions (exact-match, contains, json-schema, llm-judge) — **shipped**
- [x] **v0.2** — GitHub Action + sticky PR comments — **shipped**
- [ ] **v0.3** — Cloud sync + dashboard

Alongside the roadmap, **Cairn** opens a new pillar — test **generation** (UI today; API, unit, and docs next).

## Repositories

- **[cairn](https://github.com/plune-ai/cairn)** — autonomous agent that explores your app and generates Playwright tests.
- **[cli](https://github.com/plune-ai/cli)** — assertion test-runner for LLM behavior, with CI regression diffs.
- **[eval-action](https://github.com/plune-ai/eval-action)** — GitHub Action that runs Plune evals and gates PRs.

## Get in touch

Building — or testing — AI products? Say hello: [hello@plune.ai](mailto:hello@plune.ai).

Building from Ukraine 🇺🇦
