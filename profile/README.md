<div align="center">

# OpenInterpretability

### Probes that ship. Standards that survive.

Open-source infrastructure for mechanistic interpretability — production probes, SAE training pipelines, ProbeBench leaderboard with anti-Goodhart norms, RL-as-reward frameworks, and 51 curated papers. **Built in public. Every artifact public. Every negative result published.** All Apache-2.0.

[![Live site](https://img.shields.io/badge/live-openinterp.org-8b5cf6?style=for-the-badge)](https://openinterp.org)
[![PyPI](https://img.shields.io/pypi/v/openinterp.svg?style=for-the-badge&color=f97316)](https://pypi.org/project/openinterp/)
[![License Apache 2.0](https://img.shields.io/badge/license-Apache%202.0-green?style=for-the-badge)](https://github.com/OpenInterpretability/web/blob/main/LICENSE)
[![X @0xCVYH](https://img.shields.io/badge/X-@0xCVYH-000?style=for-the-badge)](https://x.com/0xCVYH)

</div>

---

## 🏗️ What's shipping right now

| | |
|---|---|
| 🛡️ **[FabricationGuard](https://openinterp.org/products/fabricationguard)** | Production hallucination probe on Qwen3.6-27B. AUROC 0.88 cross-task, **−88% confident-wrong reduction**, ~1ms latency. Live HF Space + ZeroGPU demo. |
| 🧬 **[ProbeBench v0.0.2](https://openinterp.org/probebench)** | First categorical leaderboard for activation probes. 8-axis ProbeScore with anti-Goodhart norms (`goodhart_resistance` axis built-in). |
| 🎬 **[Trace Theater](https://openinterp.org/observatory/trace)** | Interactive SAE feature tracing — 10 scenarios, zero login, mobile-friendly |
| 🔗 **[Circuit Canvas](https://openinterp.org/observatory/circuits)** | Figma-style attribution graphs over SAE features |
| 📊 **[InterpScore leaderboard](https://openinterp.org/interpscore)** | Public composite SAE ranking (v0.0.1, weights editable via PR) |
| 🚀 **[Training ladder](https://openinterp.org/train)** | 30-min free Colab → 4h free Kaggle → 22h paper-grade cloud |
| 📦 **`pip install openinterp`** | [PyPI v0.2.1](https://pypi.org/project/openinterp/) — FabricationGuard, ProbeBench SDK, `safe_load_qwen36_lora` utility, Atlas search, Trace generation |
| 📖 **[/research](https://openinterp.org/research)** | 51 curated canonical papers across SAE / circuits / probing / lenses / safety |

---

## 🔬 Recent findings (2026)

| Finding | Status | Artifact |
|---|---|---|
| **Probe-detected grokking in multi-probe DPO** | Validated, NeurIPS MI Workshop submission planned Sep 2026 | [nb37 v2](https://huggingface.co/datasets/caiovicentino1/openinterp-37v2-multiprobe-dpo-extended) + [nb41 v2](https://huggingface.co/datasets/caiovicentino1/openinterp-41v2-grokking-extended) — phase ratio 2.596, fresh-probe AUROC 0.472→0.528, original probes flat |
| **"Hallucination-Induction, Not Calibration"** | Submitted ICML 2026 MI Workshop, decision June 12 | Negative SAE steering result on Qwen3.6-27B + Claude-as-judge audit |
| **Multi-probe ensemble OOD walk-back** | Honest negative published | [nb46](https://huggingface.co/datasets/caiovicentino1/openinterp-46-cross-distribution-ensemble) — 0/3 datasets generalized, walked back ProbePack universal-middleware claim publicly |
| **Memory context suppresses CoT in reasoning models** | Novel observation, paper-5 reframe | [nb47](https://huggingface.co/datasets/caiovicentino1/openinterp-47-probe-gated-memory) — has_think drops 73%→50% with retrieved memories |
| **Multi-probe GRPO U-shape dynamics** | Pending behavior eval | [nb43](https://huggingface.co/datasets/caiovicentino1/openinterp-43-multiprobe-grpo-full) — peak at 77% of training, drift after; argues for val-based early stopping |
| **`.language_model.` LoRA bug + utility** | Shipped | `openinterp.safe_load_qwen36_lora()` v0.2.1+ — silent-failure fix discovered during paper-2 work, productized for community |

---

## 📂 Pick a repo

| Repo | What's in it | Lang |
|---|---|---|
| [**`web`**](https://github.com/OpenInterpretability/web) | Next.js site at **openinterp.org** — Trace Theater, Circuit Canvas, InterpScore leaderboard | TypeScript · Tailwind |
| [**`notebooks`**](https://github.com/OpenInterpretability/notebooks) | **47+ notebooks**: train SAEs from free-tier → paper-grade, multi-probe DPO/GRPO, ensemble OOD eval, probe-gated memory, grokking analysis | Jupyter · PyTorch |
| [**`cli`**](https://github.com/OpenInterpretability/cli) | `pip install openinterp` v0.2.1 — FabricationGuard, ProbeBench SDK, safe Qwen3.6 LoRA loader, Atlas, Trace | Python ≥ 3.10 |
| [**`mechreward`**](https://github.com/OpenInterpretability/mechreward) | Per-token SAE features as dense RL rewards. **+19 pp GSM8K** on Qwen3.5-4B (64% → 83% in 168 steps) | Python · TRL |
| [`.github`](https://github.com/OpenInterpretability/.github) | Org profile + shared [Code of Conduct](./CODE_OF_CONDUCT.md) + [SECURITY](./SECURITY.md) | — |

---

## 🚦 Four ways in — match your level

<table>
<tr>
<td width="25%" valign="top">

### ✨ Zero-code
Read the [manifesto](https://openinterp.org/manifesto). Share a Trace that surprised you on X tagging [@openinterp](https://x.com/openinterp). Star the repos you use.

</td>
<td width="25%" valign="top">

### 📘 Student
[Train your first SAE in 30 min](https://openinterp.org/train) on free Colab. Run [InterpScore](https://openinterp.org/interpscore) on your result. Pick a [good-first-issue](https://github.com/search?q=org%3AOpenInterpretability+is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22&type=issues).

</td>
<td width="25%" valign="top">

### 🔬 Researcher
Port a published method to a Colab we host. [Submit your SAE](https://openinterp.org/interpscore) to the public leaderboard. Author an Expedition (Q3 2026).

</td>
<td width="25%" valign="top">

### 🛡️ Safety team
Run the [Watchtower preview notebook](https://github.com/OpenInterpretability/notebooks/blob/main/notebooks/13_watchtower_preview.ipynb) on your traffic. [Request enterprise](mailto:hi@openinterp.org) early access (Q4 2026).

</td>
</tr>
</table>

More paths: [openinterp.org/contribute →](https://openinterp.org/contribute)

---

## 📊 Training ladder — any model, any scale, zero gatekeeping

| Tier | Platform | VRAM | Cost | Model | Time |
|:--|:--|:--|:--|:--|:--|
| 🚀 **[Hobbyist](https://github.com/OpenInterpretability/notebooks/blob/main/notebooks/01_hobbyist_gemma2_2b_colab.ipynb)** | Colab Free T4 | 15 GB | **$0** | Gemma-2-2B | 30–40 min |
| ⚡ **[Explorer](https://github.com/OpenInterpretability/notebooks/blob/main/notebooks/02_explorer_qwen35_4b_kaggle.ipynb)** | Kaggle 2× T4 | 32 GB | **$0** (30 h/wk) | Qwen3.5-4B (hybrid GDN) | 4–5 h |
| 👑 **[Paper-grade](https://github.com/OpenInterpretability/notebooks/blob/main/notebooks/03_papergrade_qwen36_27b_cloud.ipynb)** | Cloud RTX 6000 Pro | 96 GB | ~$30–60 | Qwen3.6-27B | 20–24 h |

Same recipe end-to-end: TopK + AuxK + HF streaming checkpoints + SAELens-compatible export.

---

## 🏛️ Four pillars

- **🔬 [Observatory](https://openinterp.org/observatory)** — see the model (Trace Theater, Circuit Canvas, Atlas, Compare)
- **🧪 [Laboratory](https://openinterp.org/laboratory)** — edit the model (Sandbox, Recipe Store, Auto-Interp, Counterfactual Studio) · Q2
- **🛡️ [Watchtower](https://openinterp.org/watchtower)** — monitor the model (Feature Firehose API, Safety Watchlist, Audit Trail) · Q4 · enterprise
- **🎓 [Academy](https://openinterp.org/academy)** — teach the world (Expeditions, Interp Olympics, Live Lectures, Repro Vault) · Q3

---

## 🗺️ Roadmap (12 months)

| Quarter | Theme | Ships |
|:--|:--|:--|
| **Q1 2026** ✅ | Observatory v0 | Trace Theater · Circuit Canvas · 23 notebooks · InterpScore v0.0.1 · `openinterp` v0.1.0 |
| **Q2 2026** (now) | Production probes + standards | ✅ FabricationGuard · ✅ ProbeBench v0.0.2 · ✅ `openinterp` v0.2.1 · ✅ ICML MI Workshop submission · paper-2 grokking writeup · cross-distribution validation |
| **Q3 2026** | Community + grants | NeurIPS MI Workshop submission · Pivotal Fellowship cohort (London Jun-Aug) · MATS Winter 2027 prep · Expeditions v1 |
| **Q4 2026** | Multi-model scaling | Cross-model probe transfer · Watchtower Enterprise beta · Reproducibility Vault |

[Full roadmap →](https://openinterp.org/roadmap) · [Manifesto →](https://openinterp.org/manifesto)

---

## 💬 Community

- 🟢 [**Good-first-issues** across all repos](https://github.com/search?q=org%3AOpenInterpretability+is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22&type=issues) — start here if you want to PR
- 💬 [Discussions](https://github.com/OpenInterpretability/web/discussions) — "which repo should this live in?" type questions
- 🤝 [Code of Conduct](./CODE_OF_CONDUCT.md) — Contributor Covenant 2.1; kindness is a feature
- ✉️ [hi@openinterp.org](mailto:hi@openinterp.org) — safety reports · partnership inquiries · Watchtower early access
- 🐦 [@openinterp on X](https://x.com/openinterp)

---

## 🙏 Standing on the shoulders of

[Neuronpedia](https://neuronpedia.org) · [Gemma Scope](https://huggingface.co/google/gemma-scope) · [SAELens](https://github.com/jbloomAus/SAELens) · [Gao et al. 2024](https://arxiv.org/abs/2406.04093) · [Marks et al. 2024](https://arxiv.org/abs/2403.19647) · [Anthropic Transformer Circuits](https://transformer-circuits.pub) · [TransformerLens](https://github.com/TransformerLensOrg/TransformerLens) · [nnsight](https://nnsight.net) · everyone before us.

---

<div align="center">

**Built in public. Every artifact public. Every negative result public.**

Apache-2.0 (code) · CC-BY 4.0 (docs) · 2026

[openinterp.org](https://openinterp.org) · [github.com/OpenInterpretability](https://github.com/OpenInterpretability) · [pypi/openinterp](https://pypi.org/project/openinterp/)

</div>
