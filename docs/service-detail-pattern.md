# Service Detail Pattern — Prototype

A worked prototype of what a managerial reporting / education tool looks
like for a single service, before we build it for all 17. Live version:
click **IT Risk Issues Management Service** (Regulatory & Issues group) in
the Process tab of the operating-model artifact linked from
[README.md](../README.md).

## The pattern

Four levels, each revealed by the one before it:

1. **Aggregate box** — the service card itself, always showing a RAG
   (Red/Amber/Green) status so health is visible without opening anything.
2. **Description** (click to expand) — what the service is and why it
   exists, in plain language. This is the "educate" half of the goal.
3. **Performance** and **Finances** (two further drill-downs, revealed
   once the box is open) — the "track and monitor" half.

**RAG roll-up rule** (proposed, not yet validated against how the
department actually wants to see this): worst-of across the underlying
KPIs — any Red KPI makes the aggregate Red, any Amber (with no Red) makes
it Amber, otherwise Green. The alternative — averaging or weighting — was
rejected for the prototype because averaging can hide a single serious
metric behind several fine ones, which defeats the point of a reporting
tool meant to surface problems.

## Worked example — IT Risk Issues Management Service

### Description

The single point of accountability for two issue workflows: **Technology
Findings** — control gaps surfaced by assessments, testing, and audits —
and **Enterprise Issues** — the subset of findings that meet materiality
thresholds and get formally elevated into the enterprise issue program,
with remediation plans, target dates, and governance reporting through to
closure.

### Performance — Technology Findings (proposed KPIs)

| KPI | Target | Why this one |
|---|---|---|
| Time to Review (intake) | ≤ 5 business days | Speed of the first human touchpoint — the most visible SLA to whoever submitted the finding |
| Rejection rate | ≤ 10% | Quality/efficiency signal in both directions: high rejection either means submitters need better guidance or reviewers are inconsistent |
| Aging backlog (past SLA) | ≤ 5% of open findings | Surfaces a growing queue before it becomes a Time-to-Review problem |

### Performance — Enterprise Issues (proposed KPIs)

| KPI | Target | Why this one |
|---|---|---|
| Time to validate & open | ≤ 10 business days | The elevation decision is higher-stakes than intake triage, so it gets a longer but still tracked SLA |
| Remediation plan rejection rate | ≤ 15% | Quality of what issue owners submit — a proxy for how well-understood the standard is across the business |
| On-time closure rate | ≥ 90% | The metric governance actually cares about: are committed issues closing when promised |

### Finances (illustrative)

| Item | Sample value |
|---|---|
| Team size | 4.5 FTE |
| Annual operating cost | $850K |
| Cost per Finding reviewed | ~$180 |
| Cost per Enterprise Issue managed | ~$2,400 |

**All figures above — Performance and Finances — are illustrative sample
data**, invented to demonstrate the mechanism (including the RAG roll-up:
the prototype shows Red, driven by the Remediation Plan Rejection Rate).
None of it should be read as, or copied into, an actual report until real
numbers replace it.

## Why this order (per the stated goal)

The brief for this tool was two-fold: **educate** (an overview anyone can
read) and **monitor** (a managerial reporting tool). The pattern maps
directly: RAG + Description serve the first audience without requiring
them to understand KPIs; Performance + Finances serve the second without
burying the first audience in numbers they didn't ask for.

## Next step

Once this box holds real data instead of illustrative placeholders, it
becomes the natural place to identify automation candidates — the
Finances panel already flags one: an estimated ~35% of Technology Findings
intake (categorization, duplicate checks, evidence completeness) is manual
today, which is the candidate first target for an agent that pre-triages
findings before a human reviews them. That agent work is out of scope for
this prototype but is the reason the box captures this data in the first
place.

## Open questions

- Does the worst-of RAG roll-up match how the department wants to see
  status, or would a different rule (e.g. weighting Enterprise Issues more
  heavily than Findings) better reflect actual risk appetite?
- Are the six proposed KPIs (three per workflow) the right ones, or does
  the team already track different metrics we should use instead of
  inventing new ones?
- Where would the real numbers for Performance and Finances come from —
  is there a system of record today, or would this be the first place
  they're captured centrally?
- Once this pattern is validated on one service, do we roll it out to all
  17, or only to a subset that's actively being monitored/reported on?
