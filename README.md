<p align="center">
  <img src="profile-anim.svg" width="100%" height="180" alt="Hyacinth of Security">
</p>

### Security engineering for AI agents · 智能体安全工程

I find and fix defects in the tooling that agents run on — doc/contract drift, dead
configuration, links that go nowhere — and I prove each one is real before opening a PR.

**86 merged pull requests across 39 upstream repositories** (2026-07 → 2026-11, 56 of
them in November), including `pipecat-ai/pipecat` (14), `microsoft/agent-framework` (8),
`labring/FastGPT` (6), `vanhauser-thc/thc-hydra` (6), `vllm-project/llm-compressor` (4),
`pytorch/torchtitan` (3), `huggingface/peft` (3).

| | |
|---|---|
| Every number here is generated from a ledger and reconciled against the GitHub API | `gh search prs --merged` |
| The defect classes are toolable, and the tools ship their false-positive cases as tests | 32 checkers with self-tests, 178 scripts total |
| I close my own PRs when the evidence goes against them | 62 stale PRs closed and archived in one pass, each with the patch kept |

#### Tooling I maintain

- **[`doc-drift`](https://github.com/lxcxjxhx/doc-drift)** — twelve stdlib-only checkers for
  documentation that stopped being true (stale docstring parameters, `#fragment` links with no
  heading, docs importing symbols the package dropped, bilingual pages that drifted apart).
  Each one was validated by replaying merged documentation-fix PRs against the commit *before*
  the fix; `run_all.py` runs the set against any tree and prints one table.

#### What I work on

- **Contract drift** — a docstring promising a parameter the signature dropped; a README
  link to a file that no longer exists; a constant nothing reads while the same literal is
  repeated in the code that should use it.
- **Agent runtime harnesses** — Pipecat (voice/streaming), Harbor (agent evaluation),
  Microsoft Agent Framework, llm-compressor.
- **Local-first AI security** — static scanning and eval tooling that runs without a
  provider key.

#### Recent upstream work

- `pipecat-ai/pipecat#6690` — `SUMMARY_TOKEN_BUFFER` was documented as the summary buffer
  but two `0.8` literals were used instead; both now read the constant. Merged 13 minutes
  after it was opened.
- `microsoft/agent-framework#10236` — CI: dropped a path filter that matched no directory.
- `harbor-framework/harbor#4213` / `#4214` — a trial lock that records what produced a
  trial's artifacts, so a regrade cannot reuse a run whose agent never ran in the target
  environment.

<sub>中文：做智能体运行时与工具链的安全工程。上游合并 86 条、覆盖 39 个仓库；每个结论都附可复核的方法，被证伪时主动撤回。</sub>
