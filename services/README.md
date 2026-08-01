# Services

This directory is where the department-wide overview (org chart, reference
architecture — see the root [README.md](../README.md)) turns into the
detail needed to actually automate something. It's organized in two
levels, and the levels are two different senses of "service" that this
project has been careful not to conflate (see the naming note in
[docs/reference-architecture.md](../docs/reference-architecture.md)):

```
services/
  <service-slug>/                  ← a reference-architecture Service
    README.md                      ← Service-level overview
    processes/
      <process-slug>/              ← one process/subprocess that delivers it
        README.md                  ← full process doc (schema.md fields)
        data/                      ← sample/synthetic data for automation work
```

- **`<service-slug>/`** — one of the 17 Services from
  [docs/reference-architecture.md](../docs/reference-architecture.md) (e.g.
  `it-risk-issues-management`). This is the coarse-grained offering shown
  in the Process tab of the operating-model artifact.
- **`processes/<process-slug>/`** — a Layer-3 `service` in the
  [docs/schema.md](../docs/schema.md) sense: one specific, documentable
  process with its own trigger, inputs, outputs, and steps. A
  reference-architecture Service is delivered by one or more of these —
  this is where the two "service" meanings connect. Documented using
  [templates/service-template.md](../templates/service-template.md).
- **`data/`** — synthetic sample data shaped like what the process
  actually handles, generated so automation work (scripts, agents) has
  something concrete to run against before real data access is wired up.
  Always synthetic unless a file explicitly says otherwise.

## Status

Only one Service is broken out so far: [it-risk-issues-management/](it-risk-issues-management/),
with one process documented: [aggregated-issues-reporting/](it-risk-issues-management/processes/aggregated-issues-reporting/).
The other 16 Services and IT Risk Issues Management Service's other
processes aren't started — add them the same way when it's time.
