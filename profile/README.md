# OpenInterpretability

**When should we believe a mechanistic interpretability claim — and where, inside a model, does a decision actually live?**

Mechanistic interpretability of long-horizon LLM agents, built on Qwen3.6-27B since April 2026: a protocol, a benchmark, a registry — and the **WANDERING arc**, an eleven-paper arc that starts with why agents fail to stop.

[openinterp.org](https://openinterp.org) · [`decision-locator`](https://github.com/OpenInterpretability/decision-locator) · [`pip install openinterp`](https://pypi.org/project/openinterp/) · [`pip install openinterp-mcp`](https://pypi.org/project/openinterp-mcp/) · [Apache-2.0](https://github.com/OpenInterpretability/web/blob/main/LICENSE)

---

## ⭐ Featured — the WANDERING arc + `decision-locator`

Long-horizon coding agents fail by **WANDERING**: they stay internally sure the task is solved but never emit the `finish` action, burning the whole turn budget. Across the first four papers (Qwen3.6-27B, SWE-bench Pro, CC-BY-4.0) we showed the agent's "task-done" verdict is linearly decodable (AUROC 0.81–0.91) yet causally inert — no residual injection rescues it, and clamping the exact, named SAE "done" feature moves the probability of finishing by −0.001 — until we found where control actually lives.

**The law:** the knowledge–action gap on agents is a *layer gap*. The decision is **known mid-stream** (the verdict, L23) but only **writable late** (L51–63, ~30 layers downstream). Patching that late, task-matched block makes a stuck agent emit a real `finish` call **42% of the time** (exact McNemar *p* = 0.031), from a 0% baseline.

🛠 **[decision-locator](https://github.com/OpenInterpretability/decision-locator)** packages the method — find & steer the commitment layer for any tool-calling decision on **any open-weight model**:

```bash
pip install git+https://github.com/OpenInterpretability/decision-locator
decision-locator demo --model gpt2     # locate → sweep → steer, on a laptop
```

📄 The arc, 11 beats, permanent DOIs (each resolves to the latest version):
**[#1 WANDERING](https://doi.org/10.5281/zenodo.20368600)** ·
[#2 It is finalization, not competence](https://doi.org/10.5281/zenodo.20490285) ·
[#3 Detect ≠ control](https://doi.org/10.5281/zenodo.20532768) ·
[#4 The lever is late](https://doi.org/10.5281/zenodo.20534218) ·
[#5 It generalizes — and it brakes](https://doi.org/10.5281/zenodo.20679286) ·
[#6 The authorization direction](https://doi.org/10.5281/zenodo.20683622) ·
[#7 Felt, not granted](https://doi.org/10.5281/zenodo.20685263) ·
[#8 The late channel](https://doi.org/10.5281/zenodo.20752895) ·
[#9 Located, not secured](https://doi.org/10.5281/zenodo.20764857) ·
[#10 The criterion cannot see what it does not measure](https://doi.org/10.5281/zenodo.21175758) ·
[#11 The action lags the answer](https://doi.org/10.5281/zenodo.21250691)
— read them at [openinterp.org/research](https://openinterp.org/research). Companion note, not a beat: [No Better Than Behavioral](https://doi.org/10.5281/zenodo.20500052).

---

## What's here

### Core protocol
| Repo | What |
|---|---|
| **[registry](https://github.com/OpenInterpretability/registry)** | Six Diagnostics schemas + reference implementation. JSON cards for probes, causal reports, intervention traces. Failed-Replication Registry data. |

### Research artifacts
| Repo | What |
|---|---|
| **[openinterp-swebench-harness](https://github.com/OpenInterpretability/openinterp-swebench-harness)** | Instrumented agent harness capturing SAE feature trajectories during agent reasoning on SWE-bench Pro. Substrate for the first four beats of the WANDERING arc. |
| **[decision-locator](https://github.com/OpenInterpretability/decision-locator)** | `pip install`-able, model-agnostic tool: find the layer where a model commits a decision, and steer it. The method behind arc beat #4, *The lever is late*. CLI + Colab + CI. |
| **[inspect-tool-entropy-collapse](https://github.com/OpenInterpretability/inspect-tool-entropy-collapse)** | The tool-entropy-collapse WANDERING detector as an Inspect eval (UK AISI `inspect_evals` submission). |
| **[mechreward](https://github.com/OpenInterpretability/mechreward)** | Mechanistic interpretability as reward signal for RL training. SAE features + GRPO + anti-Goodhart framework. |

### Developer tools
| Repo | What |
|---|---|
| **[cli](https://github.com/OpenInterpretability/cli)** | `pip install openinterp`. FabricationGuard probe + ProbeBench leaderboard + Atlas search + Trace generation. |
| **[openinterp-mcp](https://github.com/OpenInterpretability/openinterp-mcp)** | MCP server + Colab backend. Bring-your-own-agent infrastructure for mech-interp research. Claude Code · Cursor · Cline compatible. |
| **[notebooks](https://github.com/OpenInterpretability/notebooks)** | Train your first SAE in 30 min → paper-grade at 27B. Free Colab + Kaggle + cloud ladders. |

### Web
| Repo | What |
|---|---|
| **[web](https://github.com/OpenInterpretability/web)** | [openinterp.org](https://openinterp.org) — the protocol, the registry, the publications. |

---

## Why this exists

Probes that hit AUROC 0.95 at N=50 collapse at N=500. SAE features that "explain" a concept fail under matched-norm random controls. Steering vectors that flip outputs turn out to be softmax temperature shifts. CoT-redirect interventions that clear sabotage end up causing it. And a "task-done" feature that predicts finishing at AUROC 0.91 doesn't *cause* it.

We caught these in our own work — with documented walk-backs and pre-registered nulls. The protocol, and the arc's first positive, are the result.

→ Read the Six Diagnostics: [openinterp.org/research](https://openinterp.org/research)
→ Browse the Registry: [openinterp.org/atlas](https://openinterp.org/atlas)
→ Eval Standard schemas: [github.com/OpenInterpretability/registry](https://github.com/OpenInterpretability/registry)

---

**Maintainer:** [Caio Vicentino](https://orcid.org/0009-0003-4331-6259) · caio@openinterp.org · Fortaleza, Brazil
**License:** Apache-2.0 (code) · CC-BY-4.0 (documentation)
**Collaborate:** caio@openinterp.org
