# Sample Data — Aggregated Issues Reporting

**All files here are synthetic**, generated on 2026-08-01 to give
automation prototyping something realistic to run against. No real
finding, issue, audit result, or person is represented. Field names and
value ranges are a reasonable guess at what the three source systems
export — confirm against the real system exports before building
anything that depends on exact column names.

| File | Represents | Rows |
|---|---|---|
| `findings_extract.csv` | Step 2 pull from the Findings system | 10 |
| `enterprise_issues_extract.csv` | Step 2 pull from the Enterprise Issues system | 8 |
| `internal_audit_extract.csv` | Step 2 pull from the Internal Audit system | 6 |
| `master_file_2026-08-01.csv` | Step 3–4 output: the integrated, dated master file | 24 |

## Schema notes

- `findings_extract.csv`: `Finding_ID, Title, Function, Subteam, Severity, Status, Date_Identified, Target_Remediation_Date, Owner, Region, Business, Risk_Category`
- `enterprise_issues_extract.csv`: `Issue_ID, Title, Linked_Finding_ID, Risk_Rating, Status, Region, Business, Risk_Category, Target_Remediation_Date, Owner`
- `internal_audit_extract.csv`: `Audit_Finding_ID, Audit_Name, Rating, Status, Due_Date, Owner, Region, Business, Risk_Category`
- `master_file_2026-08-01.csv`: `Master_ID, Source_System, Source_ID, Title, Severity_Rating, Status, Owner, Region, Business, Risk_Category, Due_Date, As_Of_Date` —
  the common schema step 3 (integration) maps all three sources into. The
  mapping itself (e.g. Enterprise Issues' `Risk_Rating` → `Severity_Rating`,
  Internal Audit's `Rating` → `Severity_Rating`) is a modeling choice made
  here for the prototype — confirm it matches how the team actually wants
  severities normalized across three systems that don't share a scale.
- `Linked_Finding_ID` on a couple of Enterprise Issues rows is intentionally
  blank — not every escalated issue in this sample traces back to a single
  Finding, which is realistic and worth handling in any automation rather
  than assuming a clean 1:1 link.
- **`Region`, `Business`, and `Risk_Category` were added** when building
  the Aggregated Issues Summary report (filters need something to filter
  *on*) — they weren't in the original extract schema from the process
  doc. `Business` is a synthetic 3-value set (Technology Infrastructure,
  Enterprise, Payments) standing in for whatever LOB/business taxonomy the
  real systems use; `Risk_Category` (Access Management, Data Protection,
  Network Security, Third Party Risk, Patch Management, Application
  Security, Cloud Security, Governance & Documentation) is similarly
  invented. Both need to be confirmed against — or replaced by — real
  values once this connects to actual systems.
- **"Coming due" convention used by the report**: an issue counts toward
  the 30/60-day windows only if its `Status` isn't `Closed` and its
  `Due_Date` is on or after `As_Of_Date` (2026-08-01) — i.e. already-
  overdue items are excluded from "coming due," not double-counted. The
  two windows are cumulative (60-day includes everything in the 30-day
  window), matching how most aging reports read.
