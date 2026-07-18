# Kai Karlstrom

### I design and build **governed, AI-native GTM systems** — from market intelligence and targeting through execution, evaluation, and operational control.

My differentiator isn't that I automate GTM tasks. It's that I build the **production layer around those tasks** — the part most agent projects skip: encoded judgment, deterministic state, capability boundaries, tenant isolation, model economics, provider portability, observability, evaluation, governance, and human accountability.

The repositories below are reference implementations and reusable architectural patterns **extracted from a private production system** that runs GTM for ~35 client workspaces. Tenant data, provider adapters, and company-specific policy remain private; what's public is the architecture, isolated to be reusable.

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

State, tenancy, capability scoping, observability, evaluation, and governance — the control planes that make agent systems safe to run in production.

</td>
<td>

Technical strategy, operating standards, build-vs-buy decisions, review templates, and the evaluation bars that keep a team's automations honest.

</td>
</tr>
</table>

---

## The portfolio as a system

These aren't ten unrelated tools. They're the layers you need to run AI-native GTM **reliably** — intelligence and targeting at the top, and a stack of control planes underneath that most automation never builds.

```
AI-native GTM platform
│
├── Intelligence & targeting
│   ├── gtm-research ............ cost-optimized, source-verified web research (free-first waterfall + shared cache)
│   └── gtm-pipeline ............ plain-English brief → qualified, enriched, sequencer-ready list (provider-portable)
│
├── Channel infrastructure
│   └── gtm-deliverability ...... recipient-side pre-send control plane (gateway-aware, account-throttled rollout)
│
├── Runtime observability
│   ├── cc-logger ............... session / sub-agent / tool-call telemetry for Claude Code → Postgres
│   └── codex-logger ............ the OpenAI Codex sibling, read from rollout files (no hooks needed)
│
├── Execution controls
│   ├── agent-guard ............. recovery-first PreToolUse controls for Claude Code, derived from real telemetry
│   └── codex-guard ............. the same enforcement engine for the Codex CLI
│
├── Quality & policy enforcement
│   └── model-eval-gate ......... eval-backed allowlist for cheap-model delegation; refuses every unproven downgrade
│
├── Knowledge governance
│   └── knowledge-graph-governance  deterministic write gate for agent-managed graphs (vocab, provenance, audit)
│
└── Platform architecture
    └── agent-tenancy ........... deterministic tenant binding + capability scoping for multi-tenant agent runtimes
```

**The through-line:** observe what agents actually do (`cc-logger` / `codex-logger`) → promote recurring failures into runtime controls (`agent-guard` / `codex-guard`) → gate model economics with evals (`model-eval-gate`) → gate durable memory (`knowledge-graph-governance`) → isolate tenants structurally (`agent-tenancy`) → and run the actual GTM motion on top (`gtm-research`, `gtm-pipeline`, `gtm-deliverability`).

---

## Repositories, by layer and maturity

| Repository | Layer | What it is | Maturity |
|---|---|---|---|
| [**gtm-research**](https://github.com/kkrlstrm/gtm-research) | Intelligence | Free-first, source-verified web-research engine with a shared cost cache | Reference impl · production-derived |
| [**gtm-pipeline**](https://github.com/kkrlstrm/gtm-pipeline) | Targeting | Plain-English brief → deduped, qualified, enriched, sequencer-ready list; provider-portable | Reference impl · production-derived |
| [**gtm-deliverability**](https://github.com/kkrlstrm/gtm-deliverability) | Channel infra | Gateway-aware, account-throttled pre-send rollout planner; sends nothing | Reference impl · production-derived |
| [**cc-logger**](https://github.com/kkrlstrm/cc-logger) | Observability | Local telemetry for Claude Code sessions, sub-agents, and tool calls | Production-used |
| [**codex-logger**](https://github.com/kkrlstrm/codex-logger) | Observability | Telemetry for the OpenAI Codex CLI, read from rollout files | Production-used |
| [**agent-guard**](https://github.com/kkrlstrm/agent-guard) | Execution control | Recovery-first runtime guardrails for Claude Code, grown from real telemetry | Production-used |
| [**codex-guard**](https://github.com/kkrlstrm/codex-guard) | Execution control | The same recoverability-first control engine for the Codex CLI | Production-used |
| [**model-eval-gate**](https://github.com/kkrlstrm/model-eval-gate) | Quality / policy | Circuit breaker for cheap-model delegation; eval-verified modes only | Reference impl · production-derived |
| [**knowledge-graph-governance**](https://github.com/kkrlstrm/knowledge-graph-governance) | Knowledge governance | Deterministic write gate for agent-managed knowledge graphs | Reference impl · production-derived |
| [**agent-tenancy**](https://github.com/kkrlstrm/agent-tenancy) | Platform architecture | Deterministic tenant binding + structurally-scoped capabilities | Reference impl · production-derived |

**Maturity legend** — *Production-used*: I run it against my own live agent workflows. *Reference implementation · production-derived*: the pattern is extracted from a system in production; the public repo isolates the reusable architecture, with tenant data, provider adapters, and company-specific policy kept private.

---

## What remains private

Some production adapters, company-specific policy layers, client datasets, and the end-to-end orchestration system remain private. The public repositories deliberately isolate the **reusable architectural patterns and reference implementations** — the architecture contract, not the proprietary implementation. That's the intended boundary, not a gap.

---

## Contact

- GitHub: [@kkrlstrm](https://github.com/kkrlstrm)
