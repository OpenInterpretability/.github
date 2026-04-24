# Contributing to OpenInterpretability

Thank you for helping build the open interpretability stack. This file is the **generic** guide that applies to every repo in the org. Each repo also has its own `CONTRIBUTING.md` with repo-specific scope.

## The TL;DR

1. **Open an issue first** if your change is more than ~20 lines of code, so we can align before you invest time.
2. **Fork → branch → PR.** Don't push directly to `main`.
3. **Include a test or a demo** for functional changes. Reviews go faster.
4. **Be honest in the PR description.** If a number didn't replicate, say so.
5. **Sign your commits** is nice-to-have, not required.
6. **MIT license** — by contributing, you agree your code is released under MIT (CC-BY 4.0 for docs).

## What we especially want

| | |
|---|---|
| 🧪 **New notebooks** | Train on a new model, replicate a 2025 paper, port an existing notebook to a new platform. See the [scope list on openinterp.org/train](https://openinterp.org/train). |
| 🌐 **Trace scenarios** | Add a domain (legal, finance, code-generation, bio) to Trace Theater. One PR = one scenario JSON. |
| 📊 **Leaderboard entries** | Run [notebook 18](https://github.com/OpenInterpretability/notebooks/blob/main/notebooks/18_interpscore_eval.ipynb) on your SAE, submit the JSON as a PR to `web/lib/leaderboard.ts`. |
| 🎓 **Expeditions** (Q3) | Interactive tutorials in `academy/` folder of `web`. |
| 🔧 **Tooling** | Plugins for SAELens, TransformerLens, nnsight, Goodfire Ember. |
| 🐛 **Bugs** | File on the right repo. Include: OS, Python version, minimal repro, traceback. |

## What we don't want

- **Marketing-heavy language.** Under-promise and ship is more valuable than over-promise and plan.
- **Notebooks that require paid API keys by default.** Free tier should always work.
- **Claims without reproducers.** If you cite a number, the notebook (or a link to one) must produce it.
- **Dependency bloat.** If a new package adds >50MB to install size, discuss in an issue first.

## Workflow details per repo

- Code style, test commands, build steps, and merge policy live in each repo's `CONTRIBUTING.md`.
- Start there after you clone.

## Questions?

- Open a [Discussion](https://github.com/OpenInterpretability/web/discussions) — not a code question, more of a "which repo should this live in" type.
- Email **hi@openinterp.org**.
- DM on X: [@openinterp](https://twitter.com/openinterp).

---

Standing on the shoulders of [Neuronpedia](https://neuronpedia.org), [Gemma Scope](https://huggingface.co/google/gemma-scope), [SAELens](https://github.com/jbloomAus/SAELens), the [Anthropic Transformer Circuits](https://transformer-circuits.pub) thread, and everyone before. We try to be good ancestors for what comes next.
