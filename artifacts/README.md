# Artifacts

Self-contained HTML snapshots of the pages published via the Artifact
tool during this project — one file each, inline CSS and vanilla JS, no
build step, no external dependencies. See the root [README.md](../README.md)
for what each one covers and what data backs it.

| File | Live version | Covers |
|---|---|---|
| `org-chart.html` | https://claude.ai/code/artifact/08aa5da3-9f33-4495-95e9-fa936c67c3a1 | Operating model: Team Overview, People/Process/Technology/Reference Material tabs, org chart, Consumer × Product × Service map |
| `it-risk-issues-management.html` | https://claude.ai/code/artifact/ae791543-54b6-4745-a6d7-434fecab19f1 | IT Risk Issues Management Service overview: fixed process nav (Reporting default), Service Performance / Issues Summary / Issue Aging Report on the sample data in `services/it-risk-issues-management/` |
| `response-management.html` | https://claude.ai/code/artifact/402cf547-0dc7-4f8e-af24-bdf2e2c6ecb8 | Response Management (Audit - Internal and External, Regulatory, Client) Service overview: fixed nav (Overview default; Audit, Regulatory, Client, Service Performance not yet built), cross-channel inquiry Overview report on the sample data in `services/response-management/` |

## Design system for future artifacts

These HTML artifacts now share a common design baseline via [design-system.css](design-system.css). Use it as the starting point for every new artifact so the project develops a consistent visual language rather than a collection of one-off pages.

### Baseline principles

- Keep a calm paper-and-ink palette with a small set of semantic tokens for paper, ink, muted, line, and status colors.
- Use serif headlines for narrative structure and monospace labels for metadata and section cues.
- Favor restrained borders, generous whitespace, and consistent card-like containers.
- Reuse shared patterns such as hero headers, stat rows, filter bars, and callouts instead of inventing new visual treatments for each artifact.

### Workflow

1. Start each new artifact with the same page shell: eyebrow, title, deck, metadata row, and labeled sections.
2. Link the page to [design-system.css](design-system.css) near the top of the HTML head.
3. Keep any page-specific styling in the existing inline style block, but make it override the shared tokens only when needed.
4. Treat the current artifacts as the first version of the design guideline for this project.

**The `<link>` only works here, in the repo copy.** The Artifact tool's
publishing target has a strict CSP that blocks external stylesheet
requests, so the *live* published version of each page must stay fully
self-contained (all CSS inline) — it can't fetch `design-system.css` at
all. The repo copies additionally carry the `<link>` tag purely for
local/GitHub viewing, since it's a no-op there (the inline `<style>`
already defines the same tokens, so the linked sheet doesn't change
anything even where it does load) — don't remove the inline tokens when
adding the link, and don't expect the link to do anything when the page
is opened via its `claude.ai/code/artifact/...` URL.

## These are snapshots, not the source of truth

The Markdown/CSV files elsewhere in this repo (`docs/`, `diagrams/`,
`services/`) are what actually gets edited and reasoned about turn to
turn. These HTML files are the rendered output at the point they were
last committed — if the live artifact gets updated in a later session
without also updating the file here, this copy will be stale. When that
happens, re-export/re-copy the file rather than hand-editing the HTML out
of sync with its live counterpart.
