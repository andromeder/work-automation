# Service Catalog — All 17 Services

Full detail for every service in the [reference architecture](reference-architecture.md),
following the pattern established in [service-detail-pattern.md](service-detail-pattern.md):
an aggregate RAG status, a description, and Performance/Finances drill-downs
— each drill-down carrying its own summary RAG. This is the durable record
behind the interactive version in the Process tab of the operating-model
artifact (link in [README.md](../README.md)).

**Everything quantitative below — every KPI value and finance figure — is
illustrative sample data**, invented to make the pattern legible and to
give the RAG mix some texture (not everything is Green). None of it is a
real measurement. Descriptions are first drafts inferred from the service
name and its place in the org/reference architecture — confirm against
how each team actually describes its own work.

## Rating rules

- **KPI RAG**: per-metric, against the stated target.
- **Performance summary RAG**: worst-of the service's KPIs.
- **Finances summary RAG**: driven by **budget variance** — ≤ 5% (over or
  under) is Green, +5–10% over is Amber, beyond +10% over is Red.
- **Overall (aggregate box) RAG**: worst-of Performance and Finances.

This is the same worst-of philosophy used for IT Risk Issues Management
Service — a single bad number should be visible at the top, not
averaged away.

## Assessment Delivery

### Application Control Assessment — `Green`

The standardized control assessment applied to in-scope applications —
produces the Application Control Assessment product and feeds the
Application Criticality Score. Runs a fixed-cycle testing calendar so
every application is reassessed on schedule rather than on request.
Candidate owner: **F8.3**.

| KPI | Target | Sample | RAG |
|---|---|---|---|
| Time to complete assessment | ≤ 15 business days | 12.1d | Green |
| Rework rate (evidence gaps) | ≤ 8% | 5% | Green |
| Assessment coverage (on schedule) | ≥ 95% | 97% | Green |

Performance: **Green**. Finances: 6 FTE · $1.1M/yr · ~$950/assessment ·
variance −2% → **Green**.

### Cloud Scorecard — `Amber`

Produces the recurring Cloud Scorecard by pulling control-posture signals
from cloud-hosted workloads into a single scored view per
application/domain. Newer than the on-prem assessment programs, so scope
and automation are still maturing. Candidate owner: **F8.2**.

| KPI | Target | Sample | RAG |
|---|---|---|---|
| Time to publish scorecard refresh | ≤ 10 business days | 13d | Amber |
| Data quality exceptions (manual fix) | ≤ 12% | 19% | Amber |
| Cloud workload coverage | ≥ 90% | 88% | Amber |

Performance: **Amber**. Finances: 3 FTE · $520K/yr · ~$310/refresh ·
variance +6% → **Amber**.

### Infrastructure Control Assessment Service — `Green`

The infrastructure counterpart to Application Control Assessment —
assesses servers, network, and platform control environments on a fixed
cycle, producing the Infrastructure Control Assessment product. Candidate
owner: **F8.4**.

| KPI | Target | Sample | RAG |
|---|---|---|---|
| Time to complete assessment | ≤ 15 business days | 13.4d | Green |
| Rework rate | ≤ 8% | 6% | Green |
| Assessment coverage | ≥ 95% | 96% | Green |

Performance: **Green**. Finances: 5 FTE · $940K/yr · ~$1,020/assessment ·
variance −1% → **Green**.

### ACA / ICA Support Request Service — `Amber`

The intake front door for both the Application and Infrastructure Control
Assessment programs — logs requests, validates scoping, and routes work
so the assessment teams don't absorb their own scheduling overhead.
Candidate owner: **F8** intake, may overlap **F5.1**.

| KPI | Target | Sample | RAG |
|---|---|---|---|
| Time to triage request | ≤ 3 business days | 4.1d | Amber |
| Requests returned (missing scoping info) | ≤ 10% | 15% | Amber |
| Backlog aging (past SLA) | ≤ 5% | 6% | Amber |

Performance: **Amber**. Finances: 2 FTE · $310K/yr · ~$65/request ·
variance +9% → **Amber**.

## Advisory & Consultation

### IT Controls Support (Control Advisory) — `Green`

Consultative control-design and interpretation support for teams preparing
for or responding to an assessment — the "ask an expert" layer alongside
the assessment services, not an assessment service itself. Candidate
owner: **F3.5**.

| KPI | Target | Sample | RAG |
|---|---|---|---|
| Time to first response | ≤ 2 business days | 1.6d | Green |
| Advisory rework rate (guidance later reversed) | ≤ 8% | 5% | Green |
| Requester satisfaction (CSAT) | ≥ 90% | 93% | Green |

Performance: **Green**. Finances: 4 FTE · $680K/yr · ~$140/request ·
variance −3% → **Green**.

### Cyber and Technology Support Service — `Amber`

General-purpose cyber and technology risk consultation for questions that
don't map to one of the named assessment/advisory services. The scope is
broad by design, which is also its main operating challenge — see the
open question on ownership in [reference-architecture.md](reference-architecture.md).
Candidate owner: **open**.

| KPI | Target | Sample | RAG |
|---|---|---|---|
| Time to first response | ≤ 3 business days | 4.3d | Amber |
| Requests re-routed (scope mismatch) | ≤ 12% | 18% | Amber |
| Requester satisfaction (CSAT) | ≥ 85% | 82% | Amber |

Performance: **Amber**. Finances: 3.5 FTE · $610K/yr · ~$205/request ·
variance +7% → **Amber**.

### Operational Risk Event Consultation Service — `Green`

Advises business and technology teams through the operational risk event
process — classifying an event, scoping its impact, and determining
whether it needs to be reported — feeding the Operational Risk Profile
product. Candidate owner: **F2.2**.

| KPI | Target | Sample | RAG |
|---|---|---|---|
| Time to initial consultation | ≤ 2 business days | 1.8d | Green |
| Event misclassification rate (reclassified later) | ≤ 10% | 7% | Green |
| Consultations completed within SLA | ≥ 90% | 94% | Green |

Performance: **Green**. Finances: 3 FTE · $520K/yr · ~$175/consultation ·
variance −4% → **Green**.

### Third Party IT Risk Advisory — `Amber`

Advises engagement owners and application teams on the IT risk dimensions
of third-party relationships — interpreting assessment results, guiding
remediation of vendor control gaps, and supporting sourcing decisions.
Candidate owner: **F4.3**.

| KPI | Target | Sample | RAG |
|---|---|---|---|
| Time to first response | ≤ 3 business days | 3.9d | Amber |
| Advisory rework rate | ≤ 10% | 13% | Amber |
| Engagement owner satisfaction (CSAT) | ≥ 88% | 85% | Amber |

Performance: **Amber**. Finances: 3 FTE · $540K/yr · ~$260/engagement ·
variance +5% → **Amber**.

### Change Initiative Risk Assessment Service — `Red`

Assesses the IT risk profile of significant change initiatives before
launch, feeding Business Environment and Impact Evaluations and Process
Environment Assessment. Demand is driven by the change portfolio, which
makes volume hard to forecast. Candidate owner: **open** (F1.2 or F2).

| KPI | Target | Sample | RAG |
|---|---|---|---|
| Time to complete pre-launch assessment | ≤ 10 business days | 14.7d | Red |
| Assessments reworked after governance review | ≤ 10% | 21% | Red |
| Initiatives assessed before launch (not after) | ≥ 95% | 81% | Red |

Performance: **Red**. Finances: 2.5 FTE · $430K/yr · ~$390/assessment ·
variance +14% → **Red**.

## Risk Data & Aggregation

### Inherent Risk API Service — `Green`

The system-facing service exposing inherent risk scores programmatically
so other tools (including the Application Criticality Score calculation)
can consume them without a manual handoff. Operated like a platform
service rather than a people-facing one. Candidate owner: **open** (F4 or
F3.3).

| KPI | Target | Sample | RAG |
|---|---|---|---|
| API availability (uptime) | ≥ 99.5% | 99.7% | Green |
| Score request error rate | ≤ 1% | 0.6% | Green |
| Time to resolve data-quality incidents | ≤ 2 business days | 1.5d | Green |

Performance: **Green**. Finances: 2 FTE · $380K/yr · ~$4/1,000 API calls ·
variance −5% → **Green**.

### RCSA Aggregation Service — `Amber`

Aggregates business-unit and process-level RCSA submissions into the
consolidated views behind BU RCSA, Process RCSA, and the Operational Risk
Profile — the roll-up layer turning individual self-assessments into a
department-wide picture. Candidate owner: **F2.4**.

| KPI | Target | Sample | RAG |
|---|---|---|---|
| Time to aggregate a submission cycle | ≤ 5 business days | 6.8d | Amber |
| Submissions returned (data-quality issues) | ≤ 10% | 16% | Amber |
| On-time submission rate from contributors | ≥ 90% | 86% | Amber |

Performance: **Amber**. Finances: 3 FTE · $560K/yr · ~$4,200/cycle ·
variance +4% → **Amber**.

### Inherent Risk Support Service — `Green`

The human counterpart to the Inherent Risk API Service — handles
exceptions automated scoring can't resolve, and supports teams disputing
or interpreting a score. Candidate owner: **open**, likely pairs with the
API service.

| KPI | Target | Sample | RAG |
|---|---|---|---|
| Time to resolve a scoring exception | ≤ 4 business days | 3.2d | Green |
| Score disputes upheld (score changed on review) | ≤ 15% | 11% | Green |
| Exceptions resolved within SLA | ≥ 90% | 93% | Green |

Performance: **Green**. Finances: 1.5 FTE · $260K/yr · ~$95/exception ·
variance −2% → **Green**.

## Reporting Support

### IT Risk Metrics Support Service — `Amber`

Builds and maintains the metrics pipeline behind the IT Metrics Dashboard
and IT Risk Reports — collecting, validating, and publishing the numbers
other services and products depend on being right. Candidate owner:
**F3.4**.

| KPI | Target | Sample | RAG |
|---|---|---|---|
| Time to publish monthly refresh (after period close) | ≤ 5 business days | 6.5d | Amber |
| Metric restatements after publication | ≤ 5% | 9% | Amber |
| Dashboard data freshness within SLA | ≥ 95% | 91% | Amber |

Performance: **Amber**. Finances: 3 FTE · $540K/yr · ~$1,600/cycle ·
variance +6% → **Amber**.

### Risk Documentation Site Support Service — `Green`

Maintains the IT Risk Documentation site — policies, procedures, and
reference material that other teams and consumers (Application SMEs,
Solution Architects) rely on being current and findable. Candidate owner:
**F3.2**.

| KPI | Target | Sample | RAG |
|---|---|---|---|
| Time to publish a documentation update | ≤ 3 business days | 2.4d | Green |
| Pages flagged out-of-date | ≤ 8% | 6% | Green |
| Site search success rate | ≥ 90% | 92% | Green |

Performance: **Green**. Finances: 1.5 FTE · $240K/yr · ~$85/update ·
variance −3% → **Green**.

## Regulatory & Issues

### Response Management (Audit - Internal and External, Regulatory, Client) — `Red`

Coordinates the department's responses to inquiries from three
directions at once — Internal Audit, External/Regulatory Audit and
examiner requests, and Client due-diligence questionnaires — pulling
evidence and subject-matter input together on each requester's clock,
which makes this one of the least forgiving SLAs in the department
(broadened from a Regulatory-only scope to cover all three inquiry
channels under one coordinating function). Candidate owner: **F5.3**.

| KPI | Target | Sample | RAG |
|---|---|---|---|
| Responses submitted by requester deadline | 100% | 88% | Red |
| Responses requiring resubmission/clarification | ≤ 10% | 19% | Red |
| Evidence requests fulfilled within internal SLA | ≥ 90% | 79% | Red |

Performance: **Red**. Finances: 3 FTE · $610K/yr · ~$3,100/response ·
variance +11% → **Red**.

### IT Risk Issues Management Service — `Red`

See [service-detail-pattern.md](service-detail-pattern.md) for the full
worked example — the single point of accountability for Technology
Findings and Enterprise Issues. Candidate owner: **F5** (general).
Performance: **Red** (driven by Enterprise Issues). Finances: 4.5 FTE ·
$850K/yr · variance +9% → **Amber**.

## Enablement

### Application Development and Automation Services — `Green`

Builds and maintains the internal tools, scripts, and integrations the
other 16 services run on — dashboards, the Inherent Risk API, workflow
automation — making it the one service whose "customers" are mostly other
services rather than external consumers. Candidate owner: **F3.3**.

| KPI | Target | Sample | RAG |
|---|---|---|---|
| Time to deliver a small enhancement | ≤ 10 business days | 8.6d | Green |
| Defects reopened after release | ≤ 10% | 7% | Green |
| Planned release commitments met | ≥ 90% | 92% | Green |

Performance: **Green**. Finances: 4 FTE · $760K/yr · ~$2,900/enhancement ·
variance −1% → **Green**.

## Portfolio roll-up (sample)

| RAG | Services |
|---|---|
| 🔴 Red | Change Initiative Risk Assessment Service, Response Management (Audit - Internal and External, Regulatory, Client), IT Risk Issues Management Service |
| 🟠 Amber | Cloud Scorecard, ACA/ICA Support Request Service, Cyber and Technology Support Service, Third Party IT Risk Advisory, RCSA Aggregation Service, IT Risk Metrics Support Service |
| 🟢 Green | Application Control Assessment, Infrastructure Control Assessment Service, IT Controls Support, Operational Risk Event Consultation Service, Inherent Risk API Service, Inherent Risk Support Service, Risk Documentation Site Support Service, Application Development & Automation Services |

3 Red, 6 Amber, 8 Green — deliberately mixed so the pattern demonstrates
what it's for. This is sample data, not a real health check.

## Open questions

- Same as [reference-architecture.md](reference-architecture.md): confirm
  each "candidate owner," resolve the ownership gaps flagged as open.
  Whoever confirms ownership is also the right person to correct these
  descriptions and pick real KPIs.
- Is worst-of the right roll-up for Performance→Overall and for the
  portfolio view, or should some services' Finances matter less than
  their Performance (or vice versa) when they conflict?
- Which of these 17 should get real data connected first? Given IT Risk
  Issues Management Service is already the worked example and already
  Red, it may be the natural pilot for going from illustrative to real.
