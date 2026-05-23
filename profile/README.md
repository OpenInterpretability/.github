# OpenInterp

**When should we believe a mechanistic interpretability claim?**

A protocol, a benchmark, and a registry — built from 11 studies on Qwen3.6-27B since launching OpenInterp in April 2026.

> 11 studies. 6 walk-backs. 1 protocol.

[openinterp.org](https://openinterp.org) · [`pip install openinterp-mcp`](https://pypi.org/project/openinterp-mcp/) · [`pip install openinterp`](https://pypi.org/project/openinterp/) · [Apache-2.0](https://github.com/OpenInterpretability/web/blob/main/LICENSE)

---

## What's here

### Core protocol
| Repo | What |
|---|---|
| **[registry](https://github.com/OpenInterpretability/registry)** | Six Diagnostics schemas + reference implementation. JSON cards for probes, causal reports, intervention traces. Failed-Replication Registry data. |

### Research artifacts
| Repo | What |
|---|---|
| **[openinterp-swebench-harness](https://github.com/OpenInterpretability/openinterp-swebench-harness)** | Instrumented agent harness for capturing SAE feature trajectories during agent reasoning on SWE-bench Pro. Substrate for 4 papers in the registry. |
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

Probes that hit AUROC 0.95 at N=50 collapse at N=500. SAE features that "explain" a concept fail under matched-norm random controls. Steering vectors that flip outputs turn out to be softmax temperature shifts. CoT-redirect interventions that clear sabotage end up causing it.

We caught these in our own work. The protocol is the result.

→ Read the Six Diagnostics: [openinterp.org/research](https://openinterp.org/research)
→ Browse the Registry: [openinterp.org/atlas](https://openinterp.org/atlas)
→ Eval Standard schemas: [github.com/OpenInterpretability/registry](https://github.com/OpenInterpretability/registry)

---

**Maintainer:** [Caio Vicentino](https://orcid.org/0009-0003-4331-6259) · caio@openinterp.org · Fortaleza, Brazil
**License:** Apache-2.0 (code) · CC-BY-4.0 (documentation)
**Collaborate:** caio@openinterp.org
