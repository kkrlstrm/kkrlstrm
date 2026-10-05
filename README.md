# Kai Karlstrom

### Platform engineering for GTM engineers.

I'm Director of GTM Engineering at Tam To Target, a B2B GTM agency. I design and run the
internal platform a team of GTM engineers builds client systems on: outbound, research,
signals and content for 38 client companies, mostly in EdTech, K-12, higher education and
gov-tech (September 2026).

The engineers are the platform's users. It gives them:

- a **catalog**: one client slug resolves that client's repo, database, Slack channel, sending
  workspace and task board, generated from a registry, never hand-edited;
- a **read-only CLI** whose command set was chosen from telemetry (the 14 commands that cover
  about 95% of real use);
- **golden paths**: published skills for the common jobs (campaign copy, dial research, list
  upload, queue grooming);
- **unattended jobs** as separate apps, with drift detection between the repo and what is deployed;
- **observability** of every agent session and tool call;
- **guardrails** derived from recorded failures, and an **eval-gated model allowlist**;
- **propose-then-apply** approval for anything that writes, sends or spends.

I design the systems and run them. Coding agents write most of the code. The telemetry is how I
know the result is right.

---

## Start here

| You are | Start with | Then |
|---|---|---|
| A platform, AI-infra or devtools engineer | [runtune](https://github.com/kkrlstrm/runtune) and its [evidence doc](https://github.com/kkrlstrm/runtune/blob/main/docs/EVIDENCE.md) | [model-eval-gate](https://github.com/kkrlstrm/model-eval-gate), [agent-tenancy](https://github.com/kkrlstrm/agent-tenancy), [internal-gtm-platform](https://github.com/kkrlstrm/internal-gtm-platform) |
| Hiring for GTM platform, GTM systems or GTM engineering leadership | [internal-gtm-platform](https://github.com/kkrlstrm/internal-gtm-platform): the layers, what they measured, the known gaps | "What it measured" below, then [gtm-engineering-operating-model](https://github.com/kkrlstrm/gtm-engineering-operating-model) |
| A GTM engineer or GTM engineering leader | [gtm-pipeline](https://github.com/kkrlstrm/gtm-pipeline), [gtm-research](https://github.com/kkrlstrm/gtm-research), [gtm-deliverability](https://github.com/kkrlstrm/gtm-deliverability) | [cc-logger](https://github.com/kkrlstrm/cc-logger) |

---

## The platform, by layer

| Layer | What it gives GTM engineers | Public reference implementation |
|---|---|---|
| Catalog and tenancy | One slug resolves every system a client has; the model never picks a tenant | [agent-tenancy](https://github.com/kkrlstrm/agent-tenancy) |
| Observability | Every agent session and tool call in one warehouse | [cc-logger](https://github.com/kkrlstrm/cc-logger) · [codex-logger](https://github.com/kkrlstrm/codex-logger) · [cursor-logger](https://github.com/kkrlstrm/cursor-logger) |
| Policy and guardrails | Rules at the tool boundary, written from recorded failures | [callusguard](https://github.com/kkrlstrm/callusguard) (components: agent-guard, codex-guard, wroteonly) |
| Harness feedback loop | Telemetry → proposed change → human approval → measured against a control | [runtune](https://github.com/kkrlstrm/runtune) |
| Model gateway | A cheaper model takes a task only after an eval clears it | [model-eval-gate](https://github.com/kkrlstrm/model-eval-gate) |
| Context and knowledge | Governed, versioned writes to shared memory | [knowledge-graph-governance](https://github.com/kkrlstrm/knowledge-graph-governance) |
| Self-service, delivery, human approval, team interfaces | CLI, published skills, fleet drift detection, propose-then-apply loops, an authority ledger, a Slack agent | Private (described in [internal-gtm-platform](https://github.com/kkrlstrm/internal-gtm-platform)) |
| Workloads on the platform | List building, research, deliverability | [gtm-pipeline](https://github.com/kkrlstrm/gtm-pipeline) · [gtm-research](https://github.com/kkrlstrm/gtm-research) · [gtm-deliverability](https://github.com/kkrlstrm/gtm-deliverability) |

---

## What it measured

- I expect the platform to double or triple how many clients each engineer can carry. It is heading that direction.
  From Q1 to Q3 2026, clients with a launched campaign per engineer rose from 5.4 to 7.5 while
  launches per engineer rose to about 19 a month. Headcount and process changed in the same
  months, so these numbers do not show the platform caused the rise. A baseline for the next
  quarter is being taken now.
  
-Q3 2026 (July to September), with the same number of GTM engineers throughout:
  - active clients rose from 27 to 37 (+37%);
  - campaigns sent to clients rose about 60%, from about 20 a week to about 32;
  - on-time delivery held steady: about 70% of campaigns reached the client on or before their
    due date, both before and after the increase;
  - meetings booked per client rose 35% (6.0 a month in Q2 to 8.0 in Q3);
  - the share of emailed leads who sent a human reply rose 32% (1.91% to 2.52%).

  
runtune was developed against about 238,000 recorded tool calls and model requests. One of its
  guard rules made failures worse until it was rewritten, and five of its recommendations changed
  once checked against production. The
  [evidence doc](https://github.com/kkrlstrm/runtune/blob/main/docs/EVIDENCE.md) keeps both.

---

## What stays private

Client data, credentials, provider adapters and company-specific policy. The public repos are
reference implementations extracted from the running platform.
