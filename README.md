# Work Automation Opportunity Mapping

This project inventories the services performed across the department, documents
their properties in a consistent way, and visualizes how they connect — as an
org chart, process diagrams, and system diagrams — so that automation
opportunities can be identified and prioritized.

## Approach

We're going slow and building up the picture in layers:

1. **Inventory** — list every service performed across the department at a
   high level (name, owning team, one-line description). Breadth first.
2. **Document** — for each service, fill in the full property set defined in
   [docs/schema.md](docs/schema.md) (inputs, outputs, tools, frequency, manual
   steps, pain points, automation potential, etc).
3. **Visualize** — generate diagrams from the documented services, organized
   along the [People / Process / Technology](docs/information-architecture.md)
   lenses (plus a Reference Material bucket for completeness checks):
   - **People** — org chart, who owns what
   - **Process** — step-by-step flow within a service
   - **Technology** — how tools/systems connect across services
4. **Analyze** — use the documented properties to rank automation
   opportunities (effort vs. impact) and report findings.

## Structure

- `services/` — one folder per reference-architecture Service, each with a
  `processes/` folder holding one folder per process/subprocess
  (`README.md` + sample `data/`). See [services/README.md](services/README.md)
  for the two-level layout and how it relates to `docs/schema.md`.
- `templates/` — the schema/template used to document each process
- `diagrams/` — Mermaid diagrams (org chart, reference architecture)
  generated from the docs
- `docs/` — schema reference and methodology notes
- `artifacts/` — committed HTML snapshots of the published, interactive
  pages (see [artifacts/README.md](artifacts/README.md)); the live links
  below are the ones to actually use, this is the backup
- `INVENTORY.md` — the running high-level list of every known service
  (name, team, status of documentation)

## Status

**The department-level view (org chart, reference architecture, artifact)
is locked for now.** Work has moved to deepening one Service at a time,
starting with [services/it-risk-issues-management/](services/it-risk-issues-management/):
trigger/inputs/outputs/steps documented for its first process
([Aggregated Issues Reporting](services/it-risk-issues-management/processes/aggregated-issues-reporting/)),
synthetic sample data generated to prototype against, and a dedicated
Service overview page (fixed header with all four processes; Reporting →
Aggregated Issues Summary is built out as a live, filterable report on
that sample data):
https://claude.ai/code/artifact/ae791543-54b6-4745-a6d7-434fecab19f1

Schema defined (matrix-aware: `function` + `subteam` + `region` +
`matrix_relationships`, see [docs/schema.md](docs/schema.md)). Layers 1–2
of the org — Head, Global IT Risk, its 8 functions, and their 30 subteams —
are documented and rendered:

- [docs/org-structure.md](docs/org-structure.md) — narrative, why it's a
  matrix, the full subteam list, and cross-link hypotheses inferred from
  subteam names (e.g. Regional Governance ↔ Governance)
- [diagrams/org-chart.md](diagrams/org-chart.md) — Mermaid source of truth
- [docs/industry-frameworks.md](docs/industry-frameworks.md) — draft
  candidate industry frameworks per function, pending validation
- [docs/information-architecture.md](docs/information-architecture.md) —
  the People / Process / Technology / Reference Material framework the
  artifact is organized around, and how it maps to the schema
- [docs/reference-architecture.md](docs/reference-architecture.md) — the
  Consumers / Products / Services taxonomy (Capabilities layer still
  pending) with a draft Product×Service map, plus
  [diagrams/reference-architecture.md](diagrams/reference-architecture.md)
  for the Mermaid source
- [docs/service-detail-pattern.md](docs/service-detail-pattern.md) — the
  pattern itself (RAG → Description → Performance/Finances, each
  drill-down carrying its own summary rating) plus the worked example,
  IT Risk Issues Management Service
- [docs/service-catalog.md](docs/service-catalog.md) — the same pattern
  applied to all 17 services: a unique description, up to 3 KPIs, and
  illustrative Performance/Finances figures for each
- Polished shareable version — Team Overview up top, then People / Process /
  Technology / Reference Material tabs. Process is now a three-column
  Consumer × Product × Service map (Consumers grouped into 7, linked to
  Products), with Consumer and Product boxes kept plain and same-sized;
  only Service boxes are interactive — a colored dot for RAG status,
  click to expand into candidate owner → description → Performance/
  Finances. Technology is still scaffolded but empty until services are
  documented:
  https://claude.ai/code/artifact/08aa5da3-9f33-4495-95e9-fa936c67c3a1

Service-level inventory (Layer 3) not yet started — see
[INVENTORY.md](INVENTORY.md). Open questions before then (which function's
services to document first, whether the cross-link hypotheses hold up, why
Operational Risk and Shared Services have no named regional subteam) are
tracked at the bottom of `docs/org-structure.md`.
