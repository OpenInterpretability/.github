# OpenInterpretability

Open-source infrastructure for mechanistic interpretability: production probes, an MCP server that lets any agent run interp on your Colab, SAE training pipelines, a public Atlas registry with Zenodo DOIs, and ProbeBench with anti-Goodhart norms. Apache-2.0 throughout.

[openinterp.org](https://openinterp.org) · [pip install openinterp-mcp](https://pypi.org/project/openinterp-mcp/) · [pip install openinterp](https://pypi.org/project/openinterp/) · [License Apache 2.0](https://github.com/OpenInterpretability/web/blob/main/LICENSE)

## What's shipping right now

| Project | Description |
|---|---|
| [openinterp-mcp v0.1.0](https://openinterp.org/mcp) | MCP server + Colab backend. 8 typed primitives (`capture_acts`, `probe_eval`, `steer`, `sae_lookup`, `causality_protocol`, …). Works with Claude Code, Cursor, Cline, OpenHands, Aider. Privacy-first — we never see your model, data, or keys. Methodology built-in (3 mandatory baselines, 5-class verdict). |
| [agent-probe-guard v0.1](https://openinterp.org/products/agent-probe-guard) | Detect-only SDK for agent capability + thinking. AUROC 0.85/0.85, p95 0.19ms, skip 21% at 86% accuracy = ~18% budget reduction. PyPI v0.3.0. |
| [FabricationGuard](https://openinterp.org/products/fabricationguard) | Production hallucination probe on Qwen3.6-27B. AUROC 0.88 cross-task, −88% confident-wrong reduction, ~1ms latency. Live HF Space + ZeroGPU demo. |
| [ProbeBench v0.0.2](https://openinterp.org/probebench) | First categorical leaderboard for activation probes. 8-axis ProbeScore with anti-Goodhart norms (`goodhart_resistance` axis built-in). |
| [Atlas registry](https://github.com/OpenInterpretability/registry) | Public index of mech-interp publications. Schema v1, Zenodo DOIs auto-issued, HF datasets per entry, citation tracking via Semantic Scholar + arXiv. |
| [Trace Theater](https://openinterp.org/observatory/trace) | Interactive SAE feature tracing — 10 scenarios, zero login, mobile-friendly. |
| [Circuit Canvas](https://openinterp.org/observatory/circuits) | Figma-style attribution graphs over SAE features. |
| [InterpScore leaderboard](https://openinterp.org/interpscore) | Public composite SAE ranking (v0.0.1, weights editable via PR). |
| [Training ladder](https://openinterp.org/train) | 30-min free Colab → 4h free Kaggle → 22h paper-grade cloud. |
| `pip install openinterp` | [PyPI v0.3.0](https://pypi.org/project/openinterp/) — agent-probe-guard, FabricationGuard, ProbeBench SDK, `safe_load_qwen36_lora`, Atlas search, Trace generation. |

## Recent findings (2026)

| Finding | Status | Artifact |
|---|---|---|
| **Saturation-direction probe levers (paper-5)** | Published draft · 5 empirical classes of probe causality unified | [paper-5](https://openinterp.org/research/papers/saturation-direction-probe-levers) — 8 probes mapped across Qwen3.6-27B; pushdown-asymmetric in 4/4 capability sites |
| **Two forms of epiphenomenal probes (paper-6)** | Methodology paper · two mechanisms documented | [paper draft](https://openinterp.org/research/papers/two-forms-epiphenomenal-probes) — softmax-temp (L43) + template-lock (L55). Foundation for `causality_protocol` 5-class verdict |
| **NLA two-tier verbalization (paper-7)** | Published · cross-model fortification on Qwen2.5-7B + Gemma-3-12B | [paper-7](https://openinterp.org/research/papers/nla-two-tier-verbalization) — uniform fve_nrm 0.880, category-spread recall 0.490; better NLA makes fve_nrm LESS informative |
| **"Hallucination-Induction, Not Calibration"** | Submitted ICML 2026 MI Workshop, decision June 12 | Negative SAE steering result on Qwen3.6-27B + Claude-as-judge audit |
| **Probe-detected grokking in multi-probe DPO** | Validated, NeurIPS MI Workshop submission planned Sep 2026 | [nb37 v2](https://huggingface.co/datasets/caiovicentino1/openinterp-37v2-multiprobe-dpo-extended) + [nb41 v2](https://huggingface.co/datasets/caiovicentino1/openinterp-41v2-grokking-extended) — phase ratio 2.596, fresh-probe AUROC 0.472→0.528 |
| **Capability locus — 4/4 pushdown-asymmetric levers** | Validated · paper-5 corpus | Phase 11 + 11b on Qwen3.6-27B SWE-bench Pro — L23/L31/L43/L55 at pre_tool/turn_end lever pushdown +34 to +60pp |
| **Memory context suppresses CoT in reasoning models** | Novel observation, paper-5 reframe | [nb47](https://huggingface.co/datasets/caiovicentino1/openinterp-47-probe-gated-memory) — has_think drops 73%→50% with retrieved memories |
| **Multi-probe ensemble OOD walk-back** | Honest negative published | [nb46](https://huggingface.co/datasets/caiovicentino1/openinterp-46-cross-distribution-ensemble) — 0/3 datasets generalized, walked back ProbePack universal-middleware claim publicly |

---

## Pick a repo

| Repo | What's in it | Lang |
|---|---|---|
| [**`openinterp-mcp`**](https://github.com/OpenInterpretability/openinterp-mcp) | **NEW.** MCP server + FastAPI Colab backend + 5 Claude Code skills + judge primitives + publish pipeline. `pip install "openinterp-mcp[server]"` | Python ≥ 3.10 |
| [**`registry`**](https://github.com/OpenInterpretability/registry) | Public Atlas index — schema v1, atlas entries, replications, ProbeBench submissions. Read at `raw.githubusercontent.com/.../index.json` | JSON |
| [**`web`**](https://github.com/OpenInterpretability/web) | Next.js site at **openinterp.org** — Trace Theater, Circuit Canvas, InterpScore, /mcp, /start | TypeScript · Tailwind |
| [**`notebooks`**](https://github.com/OpenInterpretability/notebooks) | **47+ notebooks**: train SAEs from free-tier → paper-grade, multi-probe DPO/GRPO, ensemble OOD, probe-gated memory, grokking, NLA decoupling | Jupyter · PyTorch |
| [**`cli`**](https://github.com/OpenInterpretability/cli) | `pip install openinterp` v0.3.0 — agent-probe-guard, FabricationGuard, ProbeBench SDK, safe Qwen3.6 LoRA loader, Atlas, Trace | Python ≥ 3.10 |
| [**`openinterp-swebench-harness`**](https://github.com/OpenInterpretability/openinterp-swebench-harness) | Instrumented agent harness for SAE feature trajectories on SWE-bench Pro traces. Foundation for Phase 6+ findings | Python · transformers |
| [**`mechreward`**](https://github.com/OpenInterpretability/mechreward) | Per-token SAE features as dense RL rewards. **+19 pp GSM8K** on Qwen3.5-4B (64% → 83% in 168 steps) | Python · TRL |
| [`.github`](https://github.com/OpenInterpretability/.github) | Org profile + shared [Code of Conduct](./CODE_OF_CONDUCT.md) + [SECURITY](./SECURITY.md) | — |

---

## First result in 10 minutes — via your agent

```bash
pip install "openinterp-mcp[server]"
```

1. Open the [Colab template](https://colab.research.google.com/github/OpenInterpretability/openinterp-mcp/blob/main/templates/research.ipynb) → add your `NGROK_AUTHTOKEN` to Colab Secrets → run 3 cells
2. Wire `openinterp-mcp` into your agent (Claude Code, Cursor, Cline — same JSON)
3. In your agent: `/colab-attach https://abc123.ngrok-free.app` then ask it to run `causality_protocol` on a probe direction

Total time from Colab attach to first 5-class causal verdict: **~30 seconds**. [Full guide → openinterp.org/start](https://openinterp.org/start)

---

## Four ways in — match your level

- **Zero-code** — read the [manifesto](https://openinterp.org/manifesto), share a Trace that surprised you on X tagging [@openinterp](https://x.com/openinterp), star the repos you use.
- **Student** — [train your first SAE in 30 min](https://openinterp.org/train) on free Colab, run [InterpScore](https://openinterp.org/interpscore) on your result, pick a [good-first-issue](https://github.com/search?q=org%3AOpenInterpretability+is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22&type=issues).
- **Researcher** — [install openinterp-mcp](https://openinterp.org/start), attach your Colab, run experiments via your agent, publish to the Atlas with a Zenodo DOI. ~10 min to first verdict.
- **Safety team** — run the [Watchtower preview notebook](https://github.com/OpenInterpretability/notebooks/blob/main/notebooks/13_watchtower_preview.ipynb) on your traffic. [Request enterprise](mailto:hi@openinterp.org) early access (Q4 2026).

More paths: [openinterp.org/contribute](https://openinterp.org/contribute)

---

## Training ladder — any model, any scale

| Tier | Platform | VRAM | Cost | Model | Time |
|---|---|---|---|---|---|
| [Hobbyist](https://github.com/OpenInterpretability/notebooks/blob/main/notebooks/01_hobbyist_gemma2_2b_colab.ipynb) | Colab Free T4 | 15 GB | $0 | Gemma-2-2B | 30–40 min |
| [Explorer](https://github.com/OpenInterpretability/notebooks/blob/main/notebooks/02_explorer_qwen35_4b_kaggle.ipynb) | Kaggle 2× T4 | 32 GB | $0 (30 h/wk) | Qwen3.5-4B (hybrid GDN) | 4–5 h |
| [Paper-grade](https://github.com/OpenInterpretability/notebooks/blob/main/notebooks/03_papergrade_qwen36_27b_cloud.ipynb) | Cloud RTX 6000 Pro | 96 GB | ~$30–60 | Qwen3.6-27B | 20–24 h |

Same recipe end-to-end: TopK + AuxK + HF streaming checkpoints + SAELens-compatible export.

---

## Four pillars

- [Observatory](https://openinterp.org/observatory) — see the model (Trace Theater, Circuit Canvas, Atlas, Compare)
- [Laboratory](https://openinterp.org/laboratory) — edit the model (Sandbox, Recipe Store, Auto-Interp, Counterfactual Studio) · Q2
- [Watchtower](https://openinterp.org/watchtower) — monitor the model (Feature Firehose API, Safety Watchlist, Audit Trail) · Q4 · enterprise
- [Academy](https://openinterp.org/academy) — teach the world (Expeditions, Interp Olympics, Live Lectures, Repro Vault) · Q3

---

## Roadmap (12 months)

| Quarter | Theme | Ships |
|---|---|---|
| Q1 2026 (done) | Observatory v0 | Trace Theater, Circuit Canvas, 23 notebooks, InterpScore v0.0.1, `openinterp` v0.1.0 |
| Q2 2026 (now) | MCP infrastructure + probes + papers | openinterp-mcp v0.1.0, agent-probe-guard v0.1, FabricationGuard, ProbeBench v0.0.2, `openinterp` v0.3.0, Atlas registry, ICML MI Workshop paper-1 submission, papers 5/6/7 published drafts |
| Q3 2026 | Community + grants + Atlas backfill | NeurIPS MI Workshop submission, Pivotal Fellowship cohort, MATS Winter 2027 prep, Atlas seeded with 10+ entries, daily-interp-radar live |
| Q4 2026 | Multi-model scaling | Cross-model probe transfer, Watchtower Enterprise beta, Reproducibility Vault, day-one model support |

[Full roadmap](https://openinterp.org/roadmap) · [Manifesto](https://openinterp.org/manifesto)

---

## Community

- [Good-first-issues across all repos](https://github.com/search?q=org%3AOpenInterpretability+is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22&type=issues) — start here if you want to PR
- [Discussions](https://github.com/OpenInterpretability/web/discussions) — "which repo should this live in?" type questions
- [Code of Conduct](./CODE_OF_CONDUCT.md) — Contributor Covenant 2.1
- [hi@openinterp.org](mailto:hi@openinterp.org) — safety reports, partnership inquiries, Watchtower early access
- [@openinterp on X](https://x.com/openinterp)

## Built on

[Anthropic MCP](https://modelcontextprotocol.io) · [Neuronpedia](https://neuronpedia.org) · [Gemma Scope](https://huggingface.co/google/gemma-scope) · [Qwen-Scope](https://huggingface.co/Qwen) · [SAELens](https://github.com/jbloomAus/SAELens) · [Gao et al. 2024](https://arxiv.org/abs/2406.04093) · [Marks et al. 2024](https://arxiv.org/abs/2403.19647) · [Anthropic Transformer Circuits](https://transformer-circuits.pub) · [TransformerLens](https://github.com/TransformerLensOrg/TransformerLens) · [nnsight](https://nnsight.net).

---

Apache-2.0 (code) · CC-BY 4.0 (docs) · [openinterp.org](https://openinterp.org)
