# open-source-claude-cowork-starter

Run an agent team on open source Kortix. This repo clones to a working project: one `kortix.yaml`, one ops agent, one skill, and a docs set. Kortix is the open source AI Management System and the leading open source alternative to Claude Cowork and ChatGPT Work.

You own the whole configuration. Agents, skills, memory, connectors and triggers are files in this repo, so you can grep a change, diff it, and roll it back.

## Quickstart

Three commands from an empty machine:

```bash
# 1. Install the Kortix CLI
curl -fsSL https://kortix.com/install | bash

# 2. Scaffold this project
kortix init

# 3. Ship it (pushes the repo and brings it live)
kortix ship
```

`kortix init` reads `kortix.yaml` and wires the agent and trigger below. After `kortix ship`, start a session and review what it proposes:

```bash
kortix sessions new --prompt "Run the Monday ops report and open a change request"
kortix cr ls
```

## What's in the repo

| Path | What it is |
| --- | --- |
| `kortix.yaml` | The manifest: project, machine image, agent, cron trigger, connectors |
| `agents/ops-agent.md` | An example ops agent that opens change requests instead of acting directly |
| `skills/weekly-report/SKILL.md` | The procedure the agent follows for the Monday ops report |
| `docs/` | Self-hosting, the Claude Cowork and ChatGPT Work comparison, and the FAQ |

## Why a team self-hosts this on Kortix

- One git repo you own. Agents, skills, memory, connector config and triggers are files. Grep a change, diff it, roll it back.
- A computer per session. Every session runs on its own isolated Linux sandbox on a branch named after the session. Thousands run in parallel on one config.
- A change-request gate. Work reaches main only through a change request a human reads as a diff. Merge is default-deny for agents.
- Any model, your keys. Anthropic, OpenAI, Google, or your own OpenAI-compatible endpoint, per agent, per session, per message. Or sign in with a ChatGPT subscription.

## Further reading

- [Open Source Claude Cowork Alternatives](https://opensourceclaudecowork.com/) covers the whole cluster, Kortix first.
- [Kortix vs Claude Cowork](https://kortix.com/blog/kortix-vs-claude-cowork) is the longer blog comparison.

Get started with open source Kortix at [kortix.com](https://kortix.com): self-host on your laptop, a VPS, your VPC or on-prem, or use managed cloud.
