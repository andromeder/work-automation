# Information Architecture — People / Process / Technology

Every document and diagram in this project organizes its content along
three lenses, plus a fourth bucket for supporting reference material. This
is the tab structure used in the published operating-model artifact, and
it maps directly onto the schema in [docs/schema.md](schema.md) so the
categorization isn't arbitrary — it falls out of the fields we're already
collecting.

| Lens | What it answers | Backed by | Status |
|---|---|---|---|
| **People** | Who does the work — the org itself, and who it serves. | `function`, `subteam`, `region`, [org-structure.md](org-structure.md), plus the Consumers layer in [reference-architecture.md](reference-architecture.md) | Populated — Layers 1–2, plus Consumers |
| **Process** | How the work gets packaged and delivered. | The Products and Services layers of [reference-architecture.md](reference-architecture.md); eventually also `trigger`, `frequency`, `process_steps`, `manual_steps`, `pain_points`, `automation_potential` per service | Populated — Products/Services taxonomy and map; per-service process detail still waiting on Layer 3 |
| **Technology** | What the work runs on, and how systems connect. | `systems_tools`, `inputs`, `outputs`, `dependencies` | Empty — waiting on Layer 3/4 (services) |
| **Reference Material** | Supporting context used to validate completeness, not a description of the org itself. | — (not a schema field; e.g. [industry-frameworks.md](industry-frameworks.md)) | Populated — draft, needs validation |

**Why Consumers sit under People, not their own tab:** Consumers are
who the department serves, which is the same "who" lens as the org
structure — just facing outward instead of inward. Splitting them into a
fifth tab would fragment "who's involved" across two places for no real
gain.

**Why Products/Services sit under Process, not a fifth tab:** a Product is
the named deliverable and a Service is how it gets produced — both are
about *how the work gets packaged*, which is what Process means here.
The later per-service process detail (steps, triggers, manual work) will
extend this same tab rather than replace it.

## Why a fourth bucket instead of forcing everything into three

Industry frameworks, regulatory citations, and similar completeness checks
don't describe *who*, *how*, or *what runs the work* — they describe
external standards we're checking our own documentation against. Filing
that under People/Process/Technology would misrepresent it as part of the
org rather than a lens applied to it, so it gets its own bucket:
**Reference Material**.

## How this grows

- **People** is essentially done through Layer 2 (subteams) plus
  Consumers. It'll get thin updates as leads are named and the various
  cross-link hypotheses (subteam ↔ function, service ↔ subteam) are
  confirmed or corrected.
- **Process** now has its first real content — the Products/Services
  taxonomy and map — but still owes the per-service detail (steps,
  triggers, manual work) once Layer 3 services are documented against
  [templates/service-template.md](../templates/service-template.md). Note
  the reference-architecture "Service" and the Layer-3 `service` entry are
  different grains — see the naming note in
  [reference-architecture.md](reference-architecture.md).
- **Technology** stays empty until services (Layer 3) start getting
  documented — that's where `systems_tools`/`inputs`/`outputs`/
  `dependencies` come from.
- **Reference Material** grows independently — new frameworks can be added
  or removed as they're validated, without touching People/Process/Technology.
