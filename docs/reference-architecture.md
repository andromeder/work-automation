# Reference Architecture — Consumers, Products, Services

Global IT Risk's reference architecture has four layers: **Consumers →
Products → Services → Capabilities**. This document covers the first
three; Capabilities comes later once enough Services are documented to see
what capabilities they actually share.

A quick way to read the chain: **Consumers** are who we serve. **Products**
are the named deliverables they receive (a report, a score, an
assessment). **Services** are how the department actually produces those
deliverables — the repeatable offerings a subteam runs.

**A naming note, so we don't collide with ourselves:** the "Service" layer
here is coarser-grained than the `service` entries that will eventually
live in `services/` under [docs/schema.md](schema.md). A reference-
architecture Service (e.g. "RCSA Aggregation Service") is a *named
offering* — it will likely decompose into one or more granular,
subteam-level services once we document Layer 3. Don't treat the two as
the same list.

## Consumers

Grouped for readability — this grouping is a proposed read of the list you
gave, not a confirmed classification. Correct freely.

| Group | Consumers |
|---|---|
| Governance & Leadership | Committees, T&O Group Head, Senior Leadership, Domain Owners, Team Managers |
| Embedded Risk & Advisory | Risk Leads and Embedded Risk Teams, Application SMEs, Solution Architects |
| Business & Application Ownership | Functions, LOBs, Applications, Legal Entities, Application Custodians, Engagement Owners |
| Third Party & Supplier | Supplier Management Offices |
| Security Leadership | CISO, CSO |
| Assurance, Audit & Regulatory | Internal Audit, External Audit, Regulators |
| Internal Technology Partners | Internal GS Teams |

21 consumers across 7 groups.

## Products

| Group | Products |
|---|---|
| Risk Assessments | BU RCSA, Process RCSA, Application Criticality Score, Business Environment and Impact Evaluations, Process Environment Assessment, Operational Risk Profile |
| Control Assessments | Application Control Assessment, Infrastructure Control Assessment, Payments Assessments, Cloud Scorecard, SOC1 Assessment, NIST Cybersecurity Maturity Assessment |
| Risk Reporting & Documentation | Crown Jewel Report, IT Metrics Dashboard, IT Risk Reports, IT Risk Documentation |

16 products across 3 groups.

### Candidate owners

*(Kept here as analysis, not currently shown on the Product boxes in the
artifact — those were simplified back to plain boxes so Consumer,
Product, and Service boxes stay the same size. Services still show their
owner, inside the expand.)*

Derived, not independently guessed: a product's candidate owner is the
candidate owner of the service(s) that produce it (see the Services table
below and the Product × Service map). Where that service's owner is
`open`, the product's is too. **Payments Assessments is the one
exception** — no distinct service was given for it, but F8.1 is literally
named "Payments Assessments" in [org-structure.md](org-structure.md#layer-2--subteams),
so it's tagged directly from the subteam rather than through a service.

| Product | Candidate owner |
|---|---|
| BU RCSA | F2.4 |
| Process RCSA | F2.4 |
| Application Criticality Score | _open_ |
| Business Environment and Impact Evaluations | _open_ |
| Process Environment Assessment | _open_ |
| Operational Risk Profile | F2.2 / F2.4 |
| Application Control Assessment | F8.3 |
| Infrastructure Control Assessment | F8.4 |
| Payments Assessments | F8.1 (direct subteam match, no service) |
| Cloud Scorecard | F8.2 |
| SOC1 Assessment | F3.5 |
| NIST Cybersecurity Maturity Assessment | _open_ |
| Crown Jewel Report | _open — no mapped service_ |
| IT Metrics Dashboard | F3.4 |
| IT Risk Reports | F3.4 / F5 |
| IT Risk Documentation | F3.2 |

## Services

Grouped by delivery type, with a candidate owning function/subteam from
[org-structure.md](org-structure.md) — **hypotheses**, same treatment as
the Layer 2 cross-links, not confirmed ownership.

| Group | Service | Candidate owner |
|---|---|---|
| Assessment Delivery | Application Control Assessment | F8.3 Application Control Assessments |
| Assessment Delivery | Cloud Scorecard | F8.2 Cloud Scorecard |
| Assessment Delivery | Infrastructure Control Assessment Service | F8.4 Infrastructure Control Assessments |
| Assessment Delivery | ACA / ICA Support Request Service | F8 (intake across F8.3/F8.4) — may overlap F5.1 Request Intake |
| Advisory & Consultation | IT Controls Support (Control Advisory) | F3.5 Risk and Control Advisory |
| Advisory & Consultation | Cyber and Technology Support Service | _open — no clear single owner_ |
| Advisory & Consultation | Operational Risk Event Consultation Service | F2.2 Operational Risk Events |
| Advisory & Consultation | Third Party IT Risk Advisory | F4.3 Advisory Services |
| Advisory & Consultation | Change Initiative Risk Assessment Service | _open — F1.2 Domain Governance or F2 Operational Risk_ |
| Risk Data & Aggregation | Inherent Risk API Service | _open — F4 Third Party Risk or F3.3 Data & Automation_ |
| Risk Data & Aggregation | RCSA Aggregation Service | F2.4 Risk and Control Self-Assessments |
| Risk Data & Aggregation | Inherent Risk Support Service | _open — likely pairs with Inherent Risk API Service_ |
| Reporting Support | IT Risk Metrics Support Service | F3.4 Metrics Management |
| Reporting Support | Risk Documentation Site Support Service | F3.2 Reporting (or F1.1 Policy and Procedure Management) |
| Regulatory & Issues | Regulatory Response Management Service | F5.3 Reg Response |
| Regulatory & Issues | IT Risk Issues Management Service | F5 (general — Request Intake / Client Due Diligence area) |
| Enablement | Application Development and Automation Services | F3.3 Data & Automation |

17 services across 6 groups.

## Product × Service map

This is the interconnection the rendered diagrams show
([diagrams/reference-architecture.md](../diagrams/reference-architecture.md)
for the Mermaid source; the Process tab of the operating-model artifact
for the interactive version).

**Confirmed by name match** — the product and the service that produces it
share a name, so the link is about as solid as it gets before we document
the actual process:

| Product | Service |
|---|---|
| Application Control Assessment | Application Control Assessment |
| Cloud Scorecard | Cloud Scorecard |
| Infrastructure Control Assessment | Infrastructure Control Assessment Service |

**Hypothesis** — inferred from naming/domain overlap, needs confirming:

| Product | Candidate Service(s) |
|---|---|
| BU RCSA | RCSA Aggregation Service |
| Process RCSA | RCSA Aggregation Service |
| Operational Risk Profile | RCSA Aggregation Service, Operational Risk Event Consultation Service |
| IT Metrics Dashboard | IT Risk Metrics Support Service |
| IT Risk Reports | IT Risk Metrics Support Service, IT Risk Issues Management Service |
| IT Risk Documentation | Risk Documentation Site Support Service |
| Application Criticality Score | Inherent Risk API Service, Inherent Risk Support Service |
| SOC1 Assessment | IT Controls Support (Control Advisory) |
| NIST Cybersecurity Maturity Assessment | Cyber and Technology Support Service |
| Business Environment and Impact Evaluations | Change Initiative Risk Assessment Service |
| Process Environment Assessment | Change Initiative Risk Assessment Service |
| Application Control Assessment | ACA / ICA Support Request Service (intake, alongside the confirmed link above) |
| Infrastructure Control Assessment | ACA / ICA Support Request Service (intake, alongside the confirmed link above) |

**No mapped product yet** — these look like they support the department
directly (or support other services) rather than produce one of the 16
named products:

- Regulatory Response Management Service
- Third Party IT Risk Advisory
- Application Development and Automation Services (an enabling service —
  it likely builds/maintains what other services run on, which is really a
  **Technology**-layer contribution more than a Product-layer one)

**No mapped service yet**:

- Crown Jewel Report
- Payments Assessments (F8.1 is a named subteam, but no distinct
  "Payments Assessment Service" was given — confirm whether one exists
  separately or Payments Assessments is delivered directly by the subteam)

## Consumer × Product map

Same hypothesis treatment as the Product × Service map above, but at the
**consumer group** level (the 7 groups from the Consumers section, not all
21 individual consumers — a 21×16 map would be noise, not signal). Every
product has at least one candidate consumer-group link; most have a
secondary one where the product plausibly serves two audiences.

| Product | Candidate consumer group(s) |
|---|---|
| Crown Jewel Report | Governance & Leadership, Security Leadership |
| IT Metrics Dashboard | Governance & Leadership |
| Cloud Scorecard | Business & Application Ownership |
| BU RCSA | Business & Application Ownership |
| Process RCSA | Business & Application Ownership |
| Payments Assessments | Assurance/Audit/Regulatory, Business & Application Ownership |
| Application Criticality Score | Business & Application Ownership |
| SOC1 Assessment | Assurance/Audit/Regulatory, Third Party & Supplier |
| Operational Risk Profile | Governance & Leadership |
| Application Control Assessment | Business & Application Ownership |
| Business Environment and Impact Evaluations | Business & Application Ownership |
| Process Environment Assessment | Business & Application Ownership |
| IT Risk Reports | Governance & Leadership, Security Leadership |
| IT Risk Documentation | Embedded Risk & Advisory |
| NIST Cybersecurity Maturity Assessment | Security Leadership |
| Infrastructure Control Assessment | Business & Application Ownership, Internal Technology Partners |

## Open questions

- Do the three name-matched links (Application Control Assessment, Cloud
  Scorecard, Infrastructure Control Assessment) actually mean "the service
  produces the identically-named product," or is that a coincidence worth
  double-checking?
- For every "open" candidate owner in the Services table — who actually
  runs that service?
- Is Application Development and Automation Services meant to sit in this
  Product/Service taxonomy at all, or is it better described purely as a
  Technology-layer capability?
- What does "Capabilities" (the fourth layer) look like once Services are
  fully documented — do we derive it bottom-up from repeated patterns
  across services, or is there already a target list?
- Are the Consumer × Product links above (guessed at the group level) the
  right primary/secondary audiences, or does the actual usage look
  different — e.g. does Internal Audit consume more than just SOC1/Payments
  by way of the Assurance/Audit/Regulatory group?
