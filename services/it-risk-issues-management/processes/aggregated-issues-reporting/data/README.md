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

- `findings_extract.csv`: `Finding_ID, Title, Function, Subteam, Severity, Status, Date_Identified, Target_Remediation_Date, Owner`
- `enterprise_issues_extract.csv`: `Issue_ID, Title, Linked_Finding_ID, Risk_Rating, Status, Region, Target_Remediation_Date, Owner`
- `internal_audit_extract.csv`: `Audit_Finding_ID, Audit_Name, Rating, Status, Due_Date, Owner`
- `master_file_2026-08-01.csv`: `Master_ID, Source_System, Source_ID, Title, Severity_Rating, Status, Owner, Due_Date, As_Of_Date` —
  the common schema step 3 (integration) maps all three sources into. The
  mapping itself (e.g. Enterprise Issues' `Risk_Rating` → `Severity_Rating`,
  Internal Audit's `Rating` → `Severity_Rating`) is a modeling choice made
  here for the prototype — confirm it matches how the team actually wants
  severities normalized across three systems that don't share a scale.
- `Linked_Finding_ID` on a couple of Enterprise Issues rows is intentionally
  blank — not every escalated issue in this sample traces back to a single
  Finding, which is realistic and worth handling in any automation rather
  than assuming a clean 1:1 link.
