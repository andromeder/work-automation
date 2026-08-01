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
3. **Visualize** — generate diagrams from the documented services:
   - **Org chart** — who owns what
   - **Process diagrams** — step-by-step flow within a service
   - **System diagrams** — how tools/systems connect across services
4. **Analyze** — use the documented properties to rank automation
   opportunities (effort vs. impact) and report findings.

## Structure

- `services/` — one Markdown file per service, following
  `templates/service-template.md`
- `templates/` — the schema/template used to document each service
- `diagrams/` — Mermaid diagrams (org chart, process flows, system maps)
  generated from the service docs
- `docs/` — schema reference and methodology notes
- `INVENTORY.md` — the running high-level list of every known service
  (name, team, status of documentation)

## Status

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
- Polished shareable version (click a function to expand its subteams):
  https://claude.ai/code/artifact/08aa5da3-9f33-4495-95e9-fa936c67c3a1

Service-level inventory (Layer 3) not yet started — see
[INVENTORY.md](INVENTORY.md). Open questions before then (which function's
services to document first, whether the cross-link hypotheses hold up, why
Operational Risk and Shared Services have no named regional subteam) are
tracked at the bottom of `docs/org-structure.md`.
