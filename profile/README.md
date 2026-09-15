# Plune

> **Proof for AI products.** AI quality, verified.

Plune is quality infrastructure for teams shipping with LLMs — test generation, evals with
regression gates in CI, and a platform that keeps the cases, the runs and the review queue where a
human decides what enters the suite. **Nothing enters your test suite silently** — that is the one
rule everything below is built around.

**Early, but real** — on npm, on the Marketplace, and running in CI every day on our own repositories.
The tools are open source; the platform is in an **invite-only beta**.

## Three layers

**Cairn generates** tests. **The CLI and the Action evaluate** LLM behaviour and report results.
**The platform keeps the history** and holds the queue. Use any one of them, or all three.

### 🧭 Cairn — test generation

An autonomous QA agent that explores your app and leaves a trail of tests.

- Logs in with a saved Playwright session, explores each page (ARIA snapshot + screenshot), and verifies every locator before trusting it.
- Writes methodology-grade test cases (ISO/IEC/IEEE 29119-4), then generates POM-style `@playwright/test`.
- Self-validates, self-repairs (keep-best), and self-improves via Langfuse — optional, so it runs fully offline.
- Modes `design` · `automate` · `explore`; interactive TUI. Surfaces today: UI. Next: API, unit, docs.
- `@plune-ai/cairn` **0.7.0** · Apache-2.0 · TypeScript · Node 20+

### ✅ Plune CLI + Action — evals and reporting

Assertion-testing for LLM behaviour, with regression gates in CI — and the reporter that sends any
runner's results to the platform.

- `@plune-ai/cli` runs an assertion suite against your provider (Anthropic · OpenAI · OpenRouter) and returns a pass/fail report — locally, in CI, or as a regression diff between runs. 10 assertion types, from exact-match and `json-schema` to `llm-judge` and RAG metrics.
- The same CLI reports to the platform: `plune run import` turns a **JUnit XML** or Playwright JSON report from any runner into a run — no provider key needed; `plune ingest` sends a Cairn run; `plune sync` uploads an eval run.
- Commands: `run` · `report` · `diff` · `init` · `login` · `logout` · `sync` · `ingest`, plus `run start` / `finish` / `exec` / `report` / `import` / `delete` for platform runs.
- `@plune-ai/playwright` is a Playwright reporter that sends results as the run goes — several shards into one run, no file in between.
- `eval-action` wraps the CLI: on every PR it runs your evals, diffs against the base branch, and leaves one sticky comment — optionally blocking merge on a pass→fail regression.
- `@plune-ai/cli` **0.11.0** · `@plune-ai/playwright` **0.2.3** · `eval-action` **v1.3.0** · MIT

### 🗂 Plune platform — cases, runs, review queue

The hosted half: test cases with a history, every run recorded, and the queue where machine-proposed
tests wait for a person. Cases are organised as a tree that mirrors your repository; a runner's
discovered tests can be trusted to become cases on arrival, or held for review.

- **Invite-only beta** at [beta.plune.ai](https://beta.plune.ai) — [join the waitlist](https://plune.ai/platform#waitlist).
- Documentation: [docs.plune.ai/platform](https://docs.plune.ai/platform/getting-started/) — getting started, concepts, and an API reference generated from the server itself.

## Repositories

- **[cairn](https://github.com/plune-ai/cairn)** — autonomous agent that explores your app and generates Playwright tests.
- **[cli](https://github.com/plune-ai/cli)** — the CLI (`@plune-ai/cli`) and the Playwright reporter (`@plune-ai/playwright`).
- **[eval-action](https://github.com/plune-ai/eval-action)** — GitHub Action that runs Plune evals and gates PRs.

The platform and the site live in private repositories for now.

## Get in touch

Building — or testing — AI products? Say hello: [hello@plune.ai](mailto:hello@plune.ai).
That address is also the beta's channel: a report sent there becomes a row in the punch-list, and
you hear back about the decision.

Building from Ukraine 🇺🇦

*Versions above are as of 2026-09-14; [docs.plune.ai](https://docs.plune.ai) shows the current ones.*
