# Service Inventory

Running high-level list of every known process/subprocess documented
under `services/` — see [services/README.md](services/README.md) for how
this nests under the 17 reference-architecture Services.

| Process | Service (parent) | Function | Description | Doc Status | Path |
|---|---|---|---|---|---|
| Aggregated Issues Reporting | IT Risk Issues Management Service | Regulatory, Audit & Issues Management | Pulls Findings, Enterprise Issues, and Internal Audit data into a master file and distributes a report | in-progress | [services/it-risk-issues-management/processes/aggregated-issues-reporting/](services/it-risk-issues-management/processes/aggregated-issues-reporting/) |
| Inquiry & Response Tracking | Response Management (Audit - Internal and External, Regulatory, Client) | Regulatory, Audit & Issues Management | Tracks Audit/Regulatory/Client inquiries from receipt to closed response, coordinated by an analyst but answered by a domain response owner | in-progress | [services/response-management/processes/inquiry-response-tracking/](services/response-management/processes/inquiry-response-tracking/) |

## Teams / Functions

Layers 1–2 of the operating model — see [docs/org-structure.md](docs/org-structure.md)
for the full narrative (why this is a matrix, not a tree, plus the subteam
cross-link hypotheses) and [diagrams/org-chart.md](diagrams/org-chart.md)
for the rendered charts.

| Code | Function | Type | Lead | Subteams |
|---|---|---|---|---|
| — | Head, Global IT Risk | Lead | _tbd_ | — |
| F1 | Governance | Global | _tbd_ | 3 |
| F2 | Operational Risk | Global | _tbd_ | 4 |
| F3 | Shared Services | Global | _tbd_ | 5 |
| F4 | Third Party Risk | Global | _tbd_ | 4 |
| F5 | Regulatory, Audit & Issues Management | Global | _tbd_ | 4 |
| F6 | US IT Risk | Regional | _tbd_ | 3 |
| F7 | EMEA IT Risk | Regional | _tbd_ | 3 |
| F8 | Compliance Assessments | Global | _tbd_ | 4 |

30 subteams total (24 global + 6 regional). Full subteam list in
[docs/org-structure.md](docs/org-structure.md#layer-2--subteams). Once
services are added below, each row will reference a subteam code (e.g.
`F1.2`) rather than just a function.
