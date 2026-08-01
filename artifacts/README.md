# Artifacts

Self-contained HTML snapshots of the pages published via the Artifact
tool during this project — one file each, inline CSS and vanilla JS, no
build step, no external dependencies. See the root [README.md](../README.md)
for what each one covers and what data backs it.

| File | Live version | Covers |
|---|---|---|
| `org-chart.html` | https://claude.ai/code/artifact/08aa5da3-9f33-4495-95e9-fa936c67c3a1 | Operating model: Team Overview, People/Process/Technology/Reference Material tabs, org chart, Consumer × Product × Service map |
| `it-risk-issues-management.html` | https://claude.ai/code/artifact/ae791543-54b6-4745-a6d7-434fecab19f1 | IT Risk Issues Management Service overview: fixed process nav, Aggregated Issues Summary report on the sample data in `services/it-risk-issues-management/` |

## These are snapshots, not the source of truth

The Markdown/CSV files elsewhere in this repo (`docs/`, `diagrams/`,
`services/`) are what actually gets edited and reasoned about turn to
turn. These HTML files are the rendered output at the point they were
last committed — if the live artifact gets updated in a later session
without also updating the file here, this copy will be stale. When that
happens, re-export/re-copy the file rather than hand-editing the HTML out
of sync with its live counterpart.
