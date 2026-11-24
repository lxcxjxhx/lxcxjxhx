<p align="center">
  <img src="profile-anim.svg" width="100%" alt="Hyacinth of Security — live board / flagship project / highlights">
</p>

<p align="center">
  <a href="https://github.com/search?q=author%3Alxcxjxhx+type%3Apr+is%3Amerged+-user%3Alxcxjxhx&type=pullrequests"><img src="https://img.shields.io/endpoint?url=https%3A%2F%2Fraw.githubusercontent.com%2Flxcxjxhx%2Flxcxjxhx%2Fmain%2Fstats%2Fupstream.json&style=flat-square" alt="upstream merges"></a>
  <img src="https://img.shields.io/endpoint?url=https%3A%2F%2Fraw.githubusercontent.com%2Flxcxjxhx%2Flxcxjxhx%2Fmain%2Fstats%2Frepos.json&style=flat-square" alt="repositories">
  <img src="https://img.shields.io/endpoint?url=https%3A%2F%2Fraw.githubusercontent.com%2Flxcxjxhx%2Flxcxjxhx%2Fmain%2Fstats%2Fstars.json&style=flat-square" alt="total stars">
  <img src="https://img.shields.io/endpoint?url=https%3A%2F%2Fraw.githubusercontent.com%2Flxcxjxhx%2Flxcxjxhx%2Fmain%2Fstats%2Ffollowers.json&style=flat-square" alt="followers">
</p>

<p align="center">
  <sub>SECURITY ENGINEERING FOR AI AGENTS</sub><br>
  找智能体工具链里的缺陷 → 证明它确实存在 → 再交给上游
</p>

---

### Work

I look for the defects in the tooling agents run on, and I prove each one before opening a PR.

- **Contract drift** — a docstring promising a parameter the signature dropped; a README link to a file that no longer exists; a constant nothing reads while its literal is copy-pasted.
- **Runtime harnesses** — Pipecat (voice / streaming), Harbor (agent evals), llm-compressor, NeMo.
- **Local-first security tooling** — static checks and evals that run without a provider key.

### Evidence

| artifact | claim | verify |
|:--|:--|:--|
| [`doc-drift` v0.1.0](https://github.com/lxcxjxhx/doc-drift/releases/tag/v0.1.0) | 14 stdlib-only checkers for docs that stopped being true. Every rule was validated on a real repo; the false-positive classes are written down with the repo that produced each. | `selftest ok ran=14` |
| [`doc-drift` CI](https://github.com/lxcxjxhx/doc-drift/actions) | 3 operating systems × 2 Python versions, plus a step that fails the build if a checker imports a third-party package. | green badge |
| [merged PRs](https://github.com/search?q=author%3Alxcxjxhx+type%3Apr+is%3Amerged+-user%3Alxcxjxhx&type=pullrequests) | Every merge into a repository I do not own — the count in the first badge, maintainer by maintainer, straight from GitHub search. | open, sort by repo |

> **136 findings → 2 real, 134 changed the checker.** Six repos, three ecosystems. The one that
> survived on the first pass is filed upstream
> ([`llm-compressor#3526`](https://github.com/vllm-project/llm-compressor/pull/3526)). A rule that
> only ever finds things is guessing.
>
> **Counts.** The first badge counts merges into repositories I do not own; the board's first figure
> is every merged PR on this account, own repositories included. The gap between the two is the
> point. Both come from the ledger, reconciled against the GitHub API, and dated in the commit that
> last touched `stats/`.

### Recent

- [`pipecat#6690`](https://github.com/pipecat-ai/pipecat/pull/6690) — `SUMMARY_TOKEN_BUFFER` was documented as the summary buffer, but two `0.8` literals were used instead; both now read the constant. Merged 13 minutes after it opened.
- [`harbor#4213`](https://github.com/harbor-framework/harbor/pull/4213) — a trial lock that records a digest for `agent.load_trajectory`, not just its path.
- [`harbor#4214`](https://github.com/harbor-framework/harbor/pull/4214) — a regrade reuses a trial whose source was a successful regrade, instead of re-running it.
- 62 of my own stale PRs closed and archived in one pass, each with the patch kept.

<p align="center"><sub>
32 self-tested checkers · 185 scripts · <a href="mailto:aqfxz_zh@qq.com">aqfxz_zh@qq.com</a> · Shanghai, China
</sub></p>
