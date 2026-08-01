# IT Risk Issues Management Service

Reference-architecture Service (Regulatory & Issues group). Candidate
owner: **F5** (general — see the open ownership question in
[docs/reference-architecture.md](../../docs/reference-architecture.md)).
Full description, RAG status, KPIs, and finances live in
[docs/service-catalog.md](../../docs/service-catalog.md) and the
interactive version in the Process tab of the operating-model artifact —
this folder doesn't repeat that, it's where the deeper, automation-focused
work happens.

## Description

The single point of accountability for two issue workflows: **Technology
Findings** — control gaps surfaced by assessments, testing, and audits —
and **Enterprise Issues** — the subset of findings that meet materiality
thresholds and get formally elevated into the enterprise issue program,
with remediation plans, target dates, and governance reporting through to
closure.

## Overview page

Polished, shareable version — fixed header with the four processes below
(Reporting has a dropdown for individual reports); content changes based
on what's selected. Only Reporting → Aggregated Issues Summary is built
out so far, as a filterable (Owner/Business/Region) report on the sample
data:
https://claude.ai/code/artifact/ae791543-54b6-4745-a6d7-434fecab19f1

## Processes

| Process | Status | Path |
|---|---|---|
| Review Issues | Not yet documented | — |
| Promotion to Enterprise Issues | Not yet documented | — |
| Aggregation of Issues | Documented | [processes/aggregated-issues-reporting/](processes/aggregated-issues-reporting/) |
| Reporting → Aggregated Issues Summary | Built (sample data) | overview page above |
| Reporting → Overdue &amp; Aging Report | Not yet built | — |
| Reporting → Remediation Plan Status | Not yet built | — |

This is very likely not the complete list of processes this Service
actually runs — Findings intake/triage and Enterprise Issues
validation/remediation tracking (the two workflows in the description
above) are probably each their own process too, just not documented yet.
Add them here as folders under `processes/` when we get to them.

## Why this Service, why this process first

IT Risk Issues Management Service is already documented with sample RAG =
Red (driven by a 22% Remediation Plan Rejection Rate) in
[docs/service-catalog.md](../../docs/service-catalog.md), making it a
natural pilot for going from illustrative to real. Aggregated Issues
Reporting was chosen as the first process to deepen because it's a
self-contained, mechanical, high-automation-potential workflow (pull from
three systems, merge, archive, report, distribute) — a good first target
before tackling the judgment-heavy parts of the Service (triage, plan
review).
