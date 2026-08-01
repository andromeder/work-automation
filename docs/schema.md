# Service Documentation Schema

Every service documented in `services/` follows this property set. The goal
of each field is noted so it's clear why we're collecting it — everything
here exists to support either the diagrams (org/process/system) or the
automation-opportunity analysis later.

| Field | Purpose |
|---|---|
| `name` | Unique, human-readable service name. |
| `function` | Owning function from the [operating model](../docs/org-structure.md) (e.g. Governance, Third Party Risk) — feeds the **org chart**. |
| `subteam` | Owning subteam within that function (e.g. Domain Governance, Control Testing) — see the Layer 2 table in [org-structure.md](org-structure.md). Use the subteam code (e.g. `F1.2`) for unambiguous cross-referencing. |
| `region` | Where the service is performed: `Global`, `US`, `EMEA`, or `Multi` — feeds the **regional dimension** of the org chart and the matrix view. |
| `owner` | Individual accountable for the service (role or name). |
| `description` | One or two sentences: what the service is and why it exists. |
| `trigger` | What kicks the service off (schedule, request, event). |
| `frequency` | How often it runs (e.g. daily, ~20x/month, ad hoc). |
| `inputs` | What comes in (data, requests, systems) — feeds **system diagram** edges. |
| `outputs` | What goes out (deliverable, data, decision) — feeds **system diagram** edges. |
| `systems_tools` | Software/tools/systems touched — feeds **system diagram** nodes. |
| `process_steps` | Ordered list of steps performed — feeds **process diagram**. |
| `manual_steps` | Which of the steps above are manual today (subset of `process_steps`). |
| `time_cost` | Estimated time per instance, and volume (e.g. "30 min, ~15/week"). |
| `dependencies` | Upstream/downstream services this connects to — feeds **system diagram** and cross-service edges on the **org chart**. |
| `matrix_relationships` | Other functions and/or regions this service exchanges data or requirements with (e.g. "consumes control ratings from Compliance Assessments; feeds regional issue data to Regulatory, Audit & Issues Management"). This is what makes the matrix — functional × regional — traceable rather than implied. |
| `frameworks` | Industry frameworks/standards or internal policies this service exists to satisfy, if any — see [docs/industry-frameworks.md](industry-frameworks.md). |
| `pain_points` | Known friction, errors, bottlenecks. |
| `automation_potential` | Rating (Low/Medium/High) + brief rationale — the key output field for prioritization later. |
| `status` | Documentation status: `stub`, `in-progress`, `complete`. |

## Conventions

- One file per service, at `services/<service-slug>/processes/<process-slug>/README.md`
  — nested under the reference-architecture Service it belongs to (see
  [services/README.md](../services/README.md) for why there are two
  levels and how they relate). Sample/synthetic data for that process
  lives alongside it in a `data/` folder.
- Use the frontmatter block from `templates/service-template.md` — keep field
  order consistent so the docs stay easy to scan and easy to parse later if
  we automate diagram generation from the data.
- It's fine for a service to start as a `stub` (name, team, one-line
  description only) during the breadth-first inventory pass, and get filled
  in later during the deep pass.
- `automation_potential` should not be filled in until the rest of the
  fields are populated — rating it early, before we know the manual steps
  and pain points, tends to just reflect a gut reaction rather than the
  evidence.
- The department is matrixed across **function** and **region** (see
  [docs/org-structure.md](org-structure.md)). Every service picks one
  owning `function` and one `region`, but almost always touches other
  cells of the matrix — that's what `matrix_relationships` is for. Don't
  leave it blank just because a service looks single-owner at first
  glance; the point of capturing it is to surface the cross-function and
  cross-region data/requirement dependencies that are easy to lose track
  of in a matrixed org.
