# Information Architecture — People / Process / Technology

Every document and diagram in this project organizes its content along
three lenses, plus a fourth bucket for supporting reference material. This
is the tab structure used in the published operating-model artifact, and
it maps directly onto the schema in [docs/schema.md](schema.md) so the
categorization isn't arbitrary — it falls out of the fields we're already
collecting.

| Lens | What it answers | Backed by (schema fields) | Status |
|---|---|---|---|
| **People** | Who does the work — the org itself. | `function`, `subteam`, `region`, plus [org-structure.md](org-structure.md) | Populated — Layers 1–2 |
| **Process** | How the work gets done, step by step. | `trigger`, `frequency`, `process_steps`, `manual_steps`, `pain_points`, `automation_potential` | Empty — waiting on Layer 3/4 (services) |
| **Technology** | What the work runs on, and how systems connect. | `systems_tools`, `inputs`, `outputs`, `dependencies` | Empty — waiting on Layer 3/4 (services) |
| **Reference Material** | Supporting context used to validate completeness, not a description of the org itself. | — (not a schema field; e.g. [industry-frameworks.md](industry-frameworks.md)) | Populated — draft, needs validation |

## Why a fourth bucket instead of forcing everything into three

Industry frameworks, regulatory citations, and similar completeness checks
don't describe *who*, *how*, or *what runs the work* — they describe
external standards we're checking our own documentation against. Filing
that under People/Process/Technology would misrepresent it as part of the
org rather than a lens applied to it, so it gets its own bucket:
**Reference Material**.

## How this grows

- **People** is essentially done through Layer 2 (subteams). It'll get
  thin updates as leads are named and the cross-link hypotheses in
  [org-structure.md](org-structure.md#cross-links-visible-from-the-names-alone)
  are confirmed or corrected.
- **Process** and **Technology** stay empty until services (Layer 3) start
  getting documented against [templates/service-template.md](../templates/service-template.md).
  Once a handful of services in one subteam are documented, both tabs
  should get their first real content (a process diagram, a system
  diagram) rather than staying placeholders.
- **Reference Material** grows independently — new frameworks can be added
  or removed as they're validated, without touching People/Process/Technology.
