# Operating Model — Layers 1–2

Global IT Risk is matrixed across two dimensions: **function** (what work is
done) and **region** (where it's done). Most of the department's functions
are global — they set a standard or run a program that applies everywhere —
while two functions exist specifically to execute and oversee IT risk within
a region. Any given service usually sits in one function but is shaped by,
and feeds, at least one other cell of the matrix. Capturing that explicitly
(via the `matrix_relationships` field in [docs/schema.md](schema.md)) is the
whole point of documenting this as a matrix instead of a simple tree.

## Layer 1 — Lead and Functions

| Code | Function | Type | Scope |
|---|---|---|---|
| — | **Head, Global IT Risk** | Lead | Global |
| F1 | Governance | Global (horizontal) | Sets the policies, standards, and risk governance framework the rest of the department operates under. |
| F2 | Operational Risk | Global (horizontal) | Identifies, measures, and manages IT operational risk globally. |
| F3 | Shared Services | Global (horizontal) | Common capabilities/tooling used by the other functions (e.g. reporting, data, workflow). |
| F4 | Third Party Risk | Global (horizontal) | Risk management over vendors and third parties with IT exposure. |
| F5 | Regulatory, Audit & Issues Management | Global (horizontal) | Manages regulatory exams, internal/external audit engagement, and remediation of issues. |
| F6 | US IT Risk | Regional (vertical) | Executes and oversees the global program within the US. |
| F7 | EMEA IT Risk | Regional (vertical) | Executes and oversees the global program within EMEA. |
| F8 | Compliance Assessments | Global (horizontal) | Assesses adherence to policy/regulatory requirements across the department. |

## Layer 2 — Subteams

Each function breaks into subteams. This is the level services (Layer 3)
and their processes (Layer 4) will attach to — every service documented
going forward should name the specific subteam it sits in, not just the
function, using the subteam code below.

**Global functions**

| Code | Function | Subteam |
|---|---|---|
| F1.1 | Governance | Policy and Procedure Management |
| F1.2 | Governance | Domain Governance |
| F1.3 | Governance | Service Management |
| F2.1 | Operational Risk | Operational Risk Reporting |
| F2.2 | Operational Risk | Operational Risk Events |
| F2.3 | Operational Risk | Environmental Scanning |
| F2.4 | Operational Risk | Risk and Control Self-Assessments |
| F3.1 | Shared Services | Control Testing |
| F3.2 | Shared Services | Reporting |
| F3.3 | Shared Services | Data & Automation |
| F3.4 | Shared Services | Metrics Management |
| F3.5 | Shared Services | Risk and Control Advisory |
| F4.1 | Third Party Risk | Supplier Control Assessments |
| F4.2 | Third Party Risk | Continuous Monitoring |
| F4.3 | Third Party Risk | Advisory Services |
| F4.4 | Third Party Risk | Shared Services Responsibility Assessment |
| F5.1 | Regulatory, Audit & Issues Management | Request Intake |
| F5.2 | Regulatory, Audit & Issues Management | Audit & Reg Prep |
| F5.3 | Regulatory, Audit & Issues Management | Reg Response |
| F5.4 | Regulatory, Audit & Issues Management | Client Due Diligence |
| F8.1 | Compliance Assessments | Payments Assessments |
| F8.2 | Compliance Assessments | Cloud Scorecard |
| F8.3 | Compliance Assessments | Application Control Assessments |
| F8.4 | Compliance Assessments | Infrastructure Control Assessments |

**Regional functions** — same three subteams recur in both regions:

| Code | Function | Subteam |
|---|---|---|
| F6.1 | US IT Risk | Local Assessments |
| F6.2 | US IT Risk | Regional Governance |
| F6.3 | US IT Risk | Regional Issues Management |
| F7.1 | EMEA IT Risk | Local Assessments |
| F7.2 | EMEA IT Risk | Regional Governance |
| F7.3 | EMEA IT Risk | Regional Issues Management |

24 global subteams + 6 regional subteams = **30 subteams** under 8 functions.

### Cross-links visible from the names alone

A few matrix connections are already implied by the subteam names, before
we've documented a single service. Worth confirming explicitly rather than
leaving the matrix table all `tbd`:

- **F4.4 Shared Services Responsibility Assessment** (Third Party Risk) —
  the name itself points at F3 Shared Services. Likely: this subteam
  assesses which control responsibilities sit with a shared-service
  provider vs. a third party, which means it consumes something from F3.
- **Regional Governance (F6.2 / F7.2)** likely maps to **F1 Governance**
  (Domain Governance / Policy and Procedure Management) — the in-region
  application of global policy.
- **Local Assessments (F6.1 / F7.1)** likely maps to **F8 Compliance
  Assessments** (running the Payments/Cloud/App/Infrastructure assessment
  types in-region) and possibly **F2.4 Risk and Control Self-Assessments**.
- **Regional Issues Management (F6.3 / F7.3)** likely maps to **F5
  Regulatory, Audit & Issues Management** (regional audit/exam prep and
  issue tracking feeding the global issues process).

That accounts for 4 of the 6 global functions (F1, F5, F8, and partially
F4/F2). **F2 Operational Risk and F3 Shared Services have no obviously
named regional counterpart** — open question below.

## Why this is a matrix, not a tree

F6 (US IT Risk) and F7 (EMEA IT Risk) aren't peers of F1–F5/F8 in the usual
org-chart sense — they're the regional lens on the same six global programs.
In practice this means:

- A global function (e.g. Third Party Risk) defines **what** must be done
  and the standard it must meet everywhere.
- A regional function (US or EMEA) executes it **in-region**, adapting for
  local regulatory requirements, and is accountable for the result there.
- Data and requirements flow **both ways**: global functions push
  standards/programs down to the regions; regions push local regulatory
  requirements, findings, and risk data back up to the global functions.

This is captured as a 6×2 matrix (global function × region). The cells
marked *hypothesis* come from the subteam-name cross-links above and still
need confirming at the service level; the rest are genuinely open:

| | US IT Risk | EMEA IT Risk |
|---|---|---|
| Governance | *hypothesis:* Regional Governance (F6.2) applies Domain Governance/Policy in-region | *hypothesis:* same, via F7.2 |
| Operational Risk | _tbd — no named regional counterpart_ | _tbd — no named regional counterpart_ |
| Shared Services | _tbd — no named regional counterpart_ | _tbd — no named regional counterpart_ |
| Third Party Risk | _tbd_ | _tbd_ |
| Regulatory, Audit & Issues Management | *hypothesis:* Regional Issues Management (F6.3) feeds/consumes F5 | *hypothesis:* same, via F7.3 |
| Compliance Assessments | *hypothesis:* Local Assessments (F6.1) executes F8 assessment types in-region | *hypothesis:* same, via F7.1 |

See [diagrams/org-chart.md](../diagrams/org-chart.md) for the rendered chart,
and [docs/industry-frameworks.md](industry-frameworks.md) for candidate
industry frameworks mapped to each function — used as a completeness check,
not yet confirmed as the frameworks actually governing each function.

## Open questions

- Are US and EMEA the only regions in scope today, or are APAC/LatAm handled
  by one of the global functions directly for now?
- Do the four *hypothesis* matrix links above (Governance, Regulatory/Audit/
  Issues, Compliance Assessments) hold up once we document the actual
  services, or are they wrong/incomplete?
- **F2 Operational Risk and F3 Shared Services have no named regional
  subteam** — do they operate globally with no in-region execution, or is
  their regional work folded into one of the three named regional subteams
  (e.g. Local Assessments) without it showing in the name?
- Who are the actual leads for F1–F8 and the 30 subteams (names/roles), for
  the next layer of the chart?
- Layer 3 (services) and Layer 4 (processes) come next — which function or
  subteam should we document first?
