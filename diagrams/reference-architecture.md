# Reference Architecture Diagram — Consumers × Products × Services

Source of truth for the three-layer interconnection diagram. See
[docs/reference-architecture.md](../docs/reference-architecture.md) for
the full taxonomy and the confidence levels behind each edge below. An
interactive version — with hover-to-trace links and candidate-owner (F.*)
tags on every product and service — lives in the Process tab of the
operating-model artifact linked from [README.md](../README.md).

Solid edges are confirmed by name match; dotted edges are hypotheses.
Same visual convention as [diagrams/org-chart.md](org-chart.md). Consumer
nodes use the group-level names from
[docs/reference-architecture.md](../docs/reference-architecture.md#consumers)
— all 21 individual consumers would make this unreadable.

```mermaid
flowchart LR
    subgraph Consumers["Consumers"]
        direction TB
        C_GOV["Governance & Leadership"]
        C_ERA["Embedded Risk & Advisory"]
        C_BAO["Business & Application Ownership"]
        C_TPS["Third Party & Supplier"]
        C_SEC["Security Leadership"]
        C_AAR["Assurance, Audit & Regulatory"]
        C_ITP["Internal Technology Partners"]
    end

    subgraph Products["Products"]
        direction TB
        P_CJR["Crown Jewel Report · open"]
        P_DASH["IT Metrics Dashboard · F3.4"]
        P_CLOUD["Cloud Scorecard · F8.2"]
        P_BURCSA["BU RCSA · F2.4"]
        P_PRCSA["Process RCSA · F2.4"]
        P_PAY["Payments Assessments · F8.1"]
        P_ACS["Application Criticality Score · open"]
        P_SOC1["SOC1 Assessment · F3.5"]
        P_ORP["Operational Risk Profile · F2.2/F2.4"]
        P_ACA["Application Control Assessment · F8.3"]
        P_BEIE["Business Environment &amp; Impact Evaluations · open"]
        P_PEA["Process Environment Assessment · open"]
        P_ITRR["IT Risk Reports · F3.4/F5"]
        P_ITRD["IT Risk Documentation · F3.2"]
        P_NIST["NIST Cybersecurity Maturity Assessment · open"]
        P_ICA["Infrastructure Control Assessment · F8.4"]
    end

    subgraph Services["Services"]
        direction TB
        S_ACA["Application Control Assessment · F8.3"]
        S_CLOUD["Cloud Scorecard · F8.2"]
        S_ITCS["IT Controls Support (Control Advisory) · F3.5"]
        S_RRM["Response Management (Audit - Internal and External, Regulatory, Client) · F5.3"]
        S_IRAS["Inherent Risk API Service · open"]
        S_CTS["Cyber and Technology Support Service · open"]
        S_ICA["Infrastructure Control Assessment Service · F8.4"]
        S_ITRMS["IT Risk Metrics Support Service · F3.4"]
        S_RCSAAGG["RCSA Aggregation Service · F2.4"]
        S_OREC["Operational Risk Event Consultation Service · F2.2"]
        S_IRS["Inherent Risk Support Service · open"]
        S_RDSS["Risk Documentation Site Support Service · F3.2"]
        S_ACAICA["ACA / ICA Support Request Service · F8"]
        S_TPIRA["Third Party IT Risk Advisory · F4.3"]
        S_IRIM["IT Risk Issues Management Service · F5"]
        S_ADAS["Application Development &amp; Automation Services · F3.3"]
        S_CIRA["Change Initiative Risk Assessment Service · open"]
    end

    C_GOV -.-> P_CJR
    C_SEC -.-> P_CJR
    C_GOV -.-> P_DASH
    C_BAO -.-> P_CLOUD
    C_BAO -.-> P_BURCSA
    C_BAO -.-> P_PRCSA
    C_AAR -.-> P_PAY
    C_BAO -.-> P_PAY
    C_BAO -.-> P_ACS
    C_AAR -.-> P_SOC1
    C_TPS -.-> P_SOC1
    C_GOV -.-> P_ORP
    C_BAO -.-> P_ACA
    C_BAO -.-> P_BEIE
    C_BAO -.-> P_PEA
    C_GOV -.-> P_ITRR
    C_SEC -.-> P_ITRR
    C_ERA -.-> P_ITRD
    C_SEC -.-> P_NIST
    C_BAO -.-> P_ICA
    C_ITP -.-> P_ICA

    P_ACA === S_ACA
    P_CLOUD === S_CLOUD
    P_ICA === S_ICA

    P_BURCSA -.-> S_RCSAAGG
    P_PRCSA -.-> S_RCSAAGG
    P_ORP -.-> S_RCSAAGG
    P_ORP -.-> S_OREC
    P_DASH -.-> S_ITRMS
    P_ITRR -.-> S_ITRMS
    P_ITRR -.-> S_IRIM
    P_ITRD -.-> S_RDSS
    P_ACS -.-> S_IRAS
    P_ACS -.-> S_IRS
    P_SOC1 -.-> S_ITCS
    P_NIST -.-> S_CTS
    P_BEIE -.-> S_CIRA
    P_PEA -.-> S_CIRA
    P_ACA -.-> S_ACAICA
    P_ICA -.-> S_ACAICA
```

40 edges total: 3 confirmed (product↔service, by name match), 37
hypotheses (16 product↔service, 21 consumer↔product). Every Product and
Service node carries its candidate owner (the `F.*` reference key from
[docs/org-structure.md](../docs/org-structure.md)) — `open` means
ownership isn't confirmed. Unmapped-to-a-product-or-service nodes:
**Crown Jewel Report** and **Payments Assessments** on the product side;
**Response Management (Audit - Internal and External, Regulatory, Client)**,
**Third Party IT Risk Advisory**, and **Application Development &
Automation Services** on the service side. See the open questions in
[docs/reference-architecture.md](../docs/reference-architecture.md).
