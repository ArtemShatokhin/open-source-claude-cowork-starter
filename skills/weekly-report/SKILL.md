---
name: weekly-report
description: Build the Monday ops report from connected tools and open a change request.
---

# Weekly ops report

Use this skill when the `monday-ops-report` trigger fires, or when a person asks for the weekly ops report. The report is a short Markdown file under `reports/` that a human reviews as a diff.

Kortix is the open source AI Management System, and this skill is a file in the repo. The whole team shares one procedure, and every edit to it is reviewable like code.

## What the report contains

1. Window. State the ISO week and the exact start and end dates.
2. Shipped work. List merged change requests from the GitHub connector, one line each.
3. Open work. List open change requests and anything waiting on a human.
4. Blockers. Note failed runs or missing credentials, with the connector and tool call.
5. Numbers. Give each metric a value, a unit, and the period it covers.

## Procedure

1. Read the last report under `reports/` to keep the format stable.
2. Pull merged and open change requests from the `github` connector for the window.
3. Pull the week's ops thread from the `slack` connector.
4. Write `reports/<ISO-week>.md`.
5. Open one change request against `main`. Do not merge it.

## Rules

- Never invent a number. If a connector call fails, write the failure and the tool name.
- One change request per week. Do not push to `main`.
- Keep the report under 400 words.
