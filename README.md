<p align="center">
  <img src="profile-anim.svg" width="100%" height="180" alt="Hyacinth of Security">
</p>

### Security engineering for AI agents · 智能体安全工程

I find and fix defects in the tooling that agents run on — doc/contract drift, dead
configuration, links that go nowhere — and I prove each one is real before opening a PR.

**39 merged pull requests across 15 upstream repositories** (2026-10 → 2026-11),
including `pipecat-ai/pipecat` (12), `labring/FastGPT` (5), `pytorch/torchtitan` (3),
`vllm-project/llm-compressor` (3), `microsoft/agent-framework` (3).

| | |
|---|---|
| Every number above is generated from a ledger and reconciled against the GitHub API | 268 tracked items |
| The defect classes are toolable, and the tools ship their false-positive cases as tests | 87 tools, 32 with self-test |
| I close my own PRs when the evidence goes against them | 43 self-closed, each with the reason in the thread |

#### What I work on

- **Contract drift** — a docstring promising a parameter the signature dropped; a README
  link to a file that no longer exists; a constant nothing reads while the same literal is
  repeated six times elsewhere.
- **Agent runtime harnesses** — Pipecat (voice/streaming), Harbor (agent evaluation),
  Microsoft Agent Framework, llm-compressor.
- **Local-first AI security** — static scanning and eval tooling that runs without a
  provider key.

#### Recent upstream work

- `pipecat-ai/pipecat#6690` — a constant documented as the summary buffer was never read;
  six copies of the value now come from it. Merged in 40 minutes.
- `pytorch/torchtitan#5777` — dropped a proposed lint suppression and fixed the five call
  sites instead, after a reviewer showed the formatter behaves the other way.
- `harbor-framework/harbor#4195` — one value under two names, one of them unused.

<sub>中文：做智能体运行时与工具链的安全工程。上游合并 39 条、覆盖 15 个仓库；每个结论都附可复核的方法，被证伪时主动撤回。</sub>
