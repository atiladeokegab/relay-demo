# Board walkthrough (a hypothetical 24-hour hackathon)

Relay is an incident-response copilot: alerts come in, get clustered and scored, matched to runbooks, and an AI drafts a cited remediation plan that a human approves step by step. This repo is a walkthrough of the team board; no product code is being built here.

Official rules: none: this is a hypothetical event

Smoke: `test ! -f pyproject.toml || uv run pytest -q`

The product that ships is `main`: the last commit that passed the smoke check.

Board: https://github.com/users/atiladeokegab/projects/8

## Deadlines

Your agent checks these every session against the UTC column. GitHub milestones keep only the
date, so this UTC column is the clock, never the milestone.

| Deadline | Event time | UTC |
|---|---|---|
| build start | 2026-09-30T11:00+01:00 | 2026-09-30T10:00Z |
| design | 2026-09-30T12:00+01:00 | 2026-09-30T11:00Z |
| core | 2026-09-30T13:30+01:00 | 2026-09-30T12:30Z |
| code freeze | 2026-10-01T09:00+01:00 | 2026-10-01T08:00Z |
| submit | 2026-10-01T10:00+01:00 | 2026-10-01T09:00Z |

## Judging criteria

- It works live
- Clear user value
- A clear pitch

## Team

| Name | GitHub | Role |
|---|---|---|
| Atilade | @atiladeokegab | lead, backend, AI/LLM API integration, infra |
| Matrix | @Atilmatrix | designer, frontend, data, design |

The lead's agents: Zeus, Prometheus, Hermes. When this page or a review says "the lead", it may be one of them acting for the lead.
