# OpenInterpretability

> Watch language models think. Open source infrastructure for mechanistic interpretability.

[![openinterp.org](https://img.shields.io/badge/web-openinterp.org-8b5cf6)](https://openinterp.org)
[![PyPI](https://img.shields.io/pypi/v/openinterp.svg)](https://pypi.org/project/openinterp/)
[![License MIT](https://img.shields.io/badge/license-MIT-green)](LICENSE)

We build open tools, publicly trained sparse autoencoders (including the first on hybrid architectures), a live leaderboard, and feature-based RL rewards — so that any researcher, student, or safety team can actually use mechanistic interpretability on their phone, in their papers, in their deployments.

---

## Pick a repo

| Repo | What's in it |
|---|---|
| [**`web`**](https://github.com/OpenInterpretability/web) | [openinterp.org](https://openinterp.org) — the Next.js site with Trace Theater, Circuit Canvas, InterpScore leaderboard. |
| [**`notebooks`**](https://github.com/OpenInterpretability/notebooks) | 23 Colab / Kaggle notebooks: train SAEs from free-tier → paper-grade, discover features, generate traces, steer, replicate circuits, probe, compute InterpScore. |
| [**`cli`**](https://github.com/OpenInterpretability/cli) | The `openinterp` Python package (`pip install openinterp`): SDK + CLI for Atlas search, Trace generation, and more. |
| [**`mechreward`**](https://github.com/OpenInterpretability/mechreward) | Per-token SAE features as dense RL rewards (`pip install mechreward`). The Stage Gate protocol that lifts Qwen3.5-4B from 64% → 83% on GSM8K. |

---

## 🚀 How to contribute

Whether you're a student curious about interpretability, a researcher publishing a paper, or a safety engineer monitoring a deployment — there's a path in.

- **Train your first SAE** in 30 min on a free Colab T4 → [notebook 01](https://github.com/OpenInterpretability/notebooks/blob/main/notebooks/01_hobbyist_gemma2_2b_colab.ipynb)
- **Submit an SAE to the leaderboard** → [InterpScore](https://openinterp.org/interpscore)
- **Add a Trace Theater scenario** → open a PR on `web`
- **Port a notebook to a new model** → open a PR on `notebooks`
- **Found a bug or missing feature?** → open an issue on the relevant repo
- **Got a Discord / Slack that matches our vibe?** → DM [@openinterp](https://twitter.com/openinterp) on X

See the [Contributor Guide](./CONTRIBUTING.md) on any repo for specifics.

---

## Roadmap

- **Q1 2026 (now)** · Observatory live (Trace Theater, Circuit Canvas, Atlas scaffold), 23 notebooks, InterpScore v0.0.1, `openinterp` v0.1.0 on PyPI.
- **Q2 2026** · Atlas populated at 8+ models, Lab Sandbox beta, `openinterp` v0.2.0 with upload/score/steer/circuit commands.
- **Q3 2026** · Academy · Recipe Store · Interp Olympics Season 1 · 12 guided Expeditions.
- **Q4 2026** · Watchtower Enterprise design partners · Model Partner Program first launch-day release · Reproducibility Vault public.

[Read the full roadmap →](https://openinterp.org/roadmap) · [Read the manifesto →](https://openinterp.org/manifesto)

---

## License

MIT for code. CC-BY 4.0 for docs. Built by [Caio Vicentino](https://huggingface.co/caiovicentino1) + community. 2026.
