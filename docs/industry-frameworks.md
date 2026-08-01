# Industry Frameworks — Reference Map (Draft, Needs Validation)

**Status: draft candidates, not confirmed.** The frameworks below are the
ones commonly referenced by IT/technology risk functions with these names
at regulated financial institutions. They're listed here as a completeness
check — a way to sanity-check that each function's mandate is fully
accounted for — not as a claim about what your organization actually cites,
is examined against, or has adopted. Please confirm, correct, and prune this
before it's treated as authoritative. Once validated, individual services
should link back to specific frameworks via the `frameworks` field in
[docs/schema.md](schema.md).

| Function | Candidate Framework / Guidance | Issuing Body | Why it might be relevant |
|---|---|---|---|
| F1 Governance | COBIT 2019 | ISACA | IT governance and management objectives framework. |
| F1 Governance | Heightened Standards (12 CFR 30, Appendix D) | OCC | Board/risk-committee governance and three-lines-of-defense expectations for large banks. |
| F1 Governance | Enterprise Risk Management — Integrating with Strategy and Performance | COSO | Enterprise risk governance structure. |
| F2 Operational Risk | Principles for the Sound Management of Operational Risk (PSMOR) | Basel Committee | Baseline expectations for managing operational risk, including IT/technology risk. |
| F2 Operational Risk | ISO 31000 | ISO | General risk management principles and process. |
| F3 Shared Services | ITIL 4 | AXELOS | IT service management practices for shared/common capabilities. |
| F4 Third Party Risk | Interagency Guidance on Third-Party Relationships: Risk Management (2023) | OCC / FDIC / Federal Reserve | Current US supervisory expectations for managing third-party/vendor risk. |
| F4 Third Party Risk | IT Examination Handbook — "Third-Party Relationships" booklet | FFIEC | Examiner-facing detail behind the interagency guidance. |
| F4 Third Party Risk | SP 800-161 — Cyber Supply Chain Risk Management | NIST | Supply-chain/vendor cyber risk practices. |
| F5 Regulatory, Audit & Issues Management | IT Examination Handbook | FFIEC | Structure/expectations for US regulatory IT exams. |
| F5 Regulatory, Audit & Issues Management | International Professional Practices Framework (IPPF) | Institute of Internal Auditors (IIA) | Internal audit standards, relevant to how audit findings/issues are managed. |
| F6 US IT Risk | IT Examination Handbook (Management, Information Security, Business Continuity booklets) | FFIEC | Core US supervisory framework for bank IT risk. |
| F6 US IT Risk | Cybersecurity Framework (CSF) 2.0 | NIST | Widely used control/outcome framework, often mapped to internally even where not mandated. |
| F6 US IT Risk | Safeguards Rule | GLBA / FTC | US data-security requirement relevant to financial institutions. |
| F7 EMEA IT Risk | Guidelines on ICT and Security Risk Management | European Banking Authority (EBA) | EU supervisory expectations for ICT risk. |
| F7 EMEA IT Risk | Digital Operational Resilience Act (DORA) | EU | Binding EU regulation on digital operational resilience (in force 2025). |
| F7 EMEA IT Risk | Operational Resilience (SS2/21) | UK PRA | UK supervisory statement on operational resilience, relevant if UK is in EMEA's scope. |
| F7 EMEA IT Risk | General Data Protection Regulation (GDPR) | EU | Data protection requirements affecting IT risk/controls in-region. |
| F8 Compliance Assessments | ISO/IEC 27001 | ISO | Information security management system and control assessment baseline. |
| F8 Compliance Assessments | Internal Control — Integrated Framework | COSO | Basis for control self-assessment methodology. |

## How to use this

1. Confirm/correct which of these actually apply — remove anything that
   doesn't, add anything missing (especially any internal or
   region-specific regulation not listed here, e.g. other EMEA
   jurisdictions beyond the UK/EU).
2. As services are documented, tag each with the specific framework(s) it
   exists to satisfy in its `frameworks` field.
3. Once enough services are tagged, this becomes a coverage check: any
   framework with no service mapped to it is either a gap in the inventory
   or a gap in actual coverage — worth flagging either way.
