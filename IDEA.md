# The idea

The lead writes this once the team has agreed the idea, and no issue is created before it is
complete. If your task doesn't fit this page, open a change-request (AGENTS.md §7).

Grew from: Zeus's pitch (a hypothetical event, made to walk through the board).

## Problem

An on-call engineer gets forty alerts for one outage, then has to find the right runbook and
decide what to do, at 3am, under pressure.

## The idea

**Relay** turns an alert storm into a short ranked list of incidents, finds the runbook sections
that apply, and drafts a remediation plan in which every step cites its runbook. A human approves
or rejects each step.

## What we build

- Webhook receivers for two alert sources, normalised into one Incident shape
- Triage: alerts clustered into incidents and ranked by severity
- Runbook retrieval with citations (source file and line range)
- A planner behind `get_provider()`: an offline stub and a Claude provider; uncited steps are rejected
- A live dashboard: incident list, plan panel, approve or reject per step
- Slack and email notifications, and a postmortem export

## What we don't build

- Running remediation steps automatically
- Accounts, teams or on-call schedules
- Any alert source beyond the two receivers

## The demo, in one line

Replay an alert storm, watch forty alerts become one incident with a cited plan, approve two steps, export the postmortem.

## Areas and owners

Each person owns their area's directories outright (AGENTS.md §6). The core is the shared
contracts; only the lead changes it.

| Area | Directories | Owner | Issues |
|---|---|---|---|
| core | `pyproject.toml`, `relay/core/`, `tests/core/` | @atiladeokegab [Zeus] | #2 |
| ingest | `relay/ingest/`, `tests/ingest/` | @atiladeokegab [Prometheus] | #3, #16, #17, #18 |
| triage | `relay/triage/`, `tests/triage/` | @Atilmatrix | #4, #28, #29, #30 |
| runbooks | `relay/runbooks/`, `runbooks/`, `tests/runbooks/` | @atiladeokegab [Zeus] | #5, #19, #20, #21 |
| planner | `relay/planner/`, `tests/planner/` | @atiladeokegab [Zeus] | #6, #22, #23, #24, #25 |
| notify | `relay/notify/`, `tests/notify/` | @atiladeokegab [Prometheus] | #8, #26, #27 |
| postmortem | `relay/postmortem/`, `tests/postmortem/` | @Atilmatrix | #9, #35, #36, #37 |
| web | `web/` | @Atilmatrix | #7, #31, #32, #33, #34 |
| samples | `samples/` | @atiladeokegab [Zeus] | #10 |
| deploy | `deploy/`, `Dockerfile` | @atiladeokegab [Zeus] | #11 |
| design | `docs/design.md`, `docs/mockup/` | @Atilmatrix | #1 |
| submission | `docs/demo.md`, `docs/submission.md`, `docs/architecture/` | @atiladeokegab [Hermes], pool, @Atilmatrix, @atiladeokegab [Zeus] | #12, #13, #14, #15 |
