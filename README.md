# Kai Karlstrom

### Production architecture for deterministic systems built around probabilistic models.

The pattern shows up everywhere I work: a probabilistic model in the middle, and a deterministic control layer around it that makes it safe to run — tenancy, evaluation, governance, observability, capability boundaries, state, provider abstraction, and a human accountability model. **Go-to-market is my proving ground**, not the point: it's a demanding, real-money domain where I've built and now *run* this stack across ~35 client workspaces. The architecture generalizes past it.

My differentiator isn't that I automate tasks. It's that I build the **production layer around them** — the part most agent projects skip — and I lead the **function** that operates it.

---

## How I work — Build · Architect · Lead

<table>
<tr>
<th align="left" width="33%">🔧 Build</th>
<th align="left" width="33%">🏛 Architect</th>
<th align="left" width="33%">🧭 Lead</th>
</tr>
<tr valign="top">
<td>

Production workflows, provider integrations, data pipelines, and agent runtimes that run unattended against real revenue data.

</td>
<td>

State, tenancy, capability scoping, observability, evaluation, and governance — the deterministic control planes that make a probabilistic system safe to run.

</td>
<td>

The operating model for a team that runs agents: decision rights, accountability, protection, and how judgment survives when the machine does the reps.

</td>
</tr>
</table>

---

## Two entry points

The portfolio is one body of work with two faces — the systems, and the function that runs them. Start with whichever you're here for:

- **🏛 [ai-native-gtm-architecture](https://github.com/kkrlstrm/ai-native-gtm-architecture)** — the **systems view**. How the control planes compose and the invariant each one enforces. The reference implementations sit under it.
- **🧭 [gtm-engineering-operating-model](https://github.com/kkrlstrm/gtm-engineering-operating-model)** — the **leadership view**. How you set up and lead a team whose real work is directing agents. The organizational half most portfolios never show.

---

## Production Agent Systems — the series

The repositories aren't scattered tools; they're one line of inquiry into the same question — *what deterministic layer does a probabilistic model need around it to run in production?* — answered one control plane at a time.

| # | Architectural question | Repository | Status |
|---|---|---|---|
| **0** | How do the layers compose? | [ai-native-gtm-architecture](https://github.com/kkrlstrm/ai-native-gtm-architecture) | Contract |
| **1** | Deterministic tenancy | [agent-tenancy](https://github.com/kkrlstrm/agent-tenancy) | Reference impl · production-derived |
| **2** | Knowledge governance | [knowledge-graph-governance](https://github.com/kkrlstrm/knowledge-graph-governance) | Reference impl · production-derived |
| **3** | Evaluation gates | [model-eval-gate](https://github.com/kkrlstrm/model-eval-gate) | Reference impl · production-derived |
| **4** | Observability | [cc-logger](https://github.com/kkrlstrm/cc-logger) · [codex-logger](https://github.com/kkrlstrm/codex-logger) | Production-used |
| **5** | Capability boundaries & execution control | [agent-guard](https://github.com/kkrlstrm/agent-guard) · [codex-guard](https://github.com/kkrlstrm/codex-guard) | Production-used |
| **6** | Source-verified state & cost control | [gtm-research](https://github.com/kkrlstrm/gtm-research) | Reference impl · production-derived |
| **7** | Provider abstraction & portable workflow | [gtm-pipeline](https://github.com/kkrlstrm/gtm-pipeline) | Reference impl · production-derived |
| **8** | Recipient-side channel control | [gtm-deliverability](https://github.com/kkrlstrm/gtm-deliverability) | Reference impl · production-derived |
| **★** | The operating model around all of it | [gtm-engineering-operating-model](https://github.com/kkrlstrm/gtm-engineering-operating-model) | Operating doctrine |

**Maturity legend** — *Production-used*: I run it against my own live agent workflows. *Reference implementation · production-derived*: the pattern is extracted from a system in production; the public repo isolates the reusable architecture, with tenant data, provider adapters, and company-specific policy kept private.

---

## As layers

The same repositories, grouped by where they sit in the stack:

```
AI-native platform  (proving ground: go-to-market)
│
├── Intelligence & targeting     gtm-research · gtm-pipeline
├── Channel infrastructure       gtm-deliverability
├── Runtime observability        cc-logger · codex-logger
├── Execution controls           agent-guard · codex-guard
├── Quality & policy enforcement model-eval-gate
├── Knowledge governance         knowledge-graph-governance
└── Platform architecture        agent-tenancy
        │
        └── operated by a team, per → gtm-engineering-operating-model
```

**The through-line:** observe what agents actually do → promote recurring failures into runtime controls → gate model economics with evals → gate durable memory → isolate tenants structurally → run the motion on top → and lead the humans who own all of it.

---

## Writing — the thinking behind the leadership model

Published essays on what leadership becomes when a team's real work is directing agents. These are the arguments the [operating model](https://github.com/kkrlstrm/gtm-engineering-operating-model) is distilled from.

- [The Layer Question — where leaders belong when teams run AI](https://www.linkedin.com/pulse/layer-question-where-leaders-belong-when-teams-run-ai-kai-karlstrom-qnzae)
- [The Expertise Need Is Dissolving — Protection Is What Leaders Provision Now](https://www.linkedin.com/pulse/expertise-need-dissolving-protection-what-leaders-now-kai-karlstrom-ea5ae/)
- [Leadership in the Age of AI Agents (The Leader as Friction)](https://www.linkedin.com/pulse/leadership-age-ai-agents-kai-karlstrom-umdfe)
- [Developing Taste — the only leadership skill that survives the agent](https://www.linkedin.com/pulse/developing-taste-only-leadership-skill-survives-agent-kai-karlstrom-zywxe)
- [The Taste Famine — transferring judgment when agents have eaten the reps](https://www.linkedin.com/pulse/how-transfer-judgment-when-agents-have-eaten-reps-kai-karlstrom-2vyoe/)
- [Permission for Inarticulate Doubt](https://www.linkedin.com/pulse/permission-inarticulate-doubt-kai-karlstrom-5glue)
- [The Builder's Trap — why the faster leader should give the build away](https://www.linkedin.com/pulse/builders-trap-why-leaders-should-delegate-age-ai-kai-karlstrom-opsje/)

---

## What remains private

Some production adapters, company-specific policy layers, client datasets, and the end-to-end orchestration system remain private. The public repositories deliberately isolate the **reusable architectural patterns and reference implementations** — the architecture contract, not the proprietary implementation. That's the intended boundary, not a gap.

---

## Contact

- GitHub: [@kkrlstrm](https://github.com/kkrlstrm)
