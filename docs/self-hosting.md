# Self-hosting open source Kortix

Self-host open source Kortix on a Linux box with one Docker Compose stack. The same `kortix.yaml` runs on your laptop, a VPS, your VPC, or on-prem, and it is the same manifest the managed cloud reads.

## Start the stack

```bash
curl -fsSL https://kortix.com/install | bash   # install the CLI
kortix self-host start                          # bring up one Docker Compose stack
```

`kortix self-host start` pulls the images and starts the API, the agent runtime, Postgres, and file storage. It prints the local URL when the stack is healthy. To run this starter against the stack:

```bash
git clone <this repo>
cd open-source-claude-cowork-starter
kortix self-host start
kortix ship
```

`kortix ship` pushes the repo and brings the project live. Sessions then start from the CLI, the web app, Slack or Teams, a cron trigger, or a signed webhook.

## What runs where

- The control plane is the Docker Compose stack on your machine: API, agent runtime, Postgres, and file storage.
- Each session boots its own isolated Linux sandbox on a branch named after the session. The sandbox is disposable, so the agent can install, run, and break anything, and only what it commits survives.
- Each connector credential is brokered server-side and never enters the sandbox. Every tool call is allow, ask, or block, down to the arguments.
- Work reaches main only through a change request a human reads as a diff. Merge is default-deny for agents.

An instance keeps its state under `~/.config/kortix/self-host/<instance>/`: Postgres data in `volumes/db/data`, files in `volumes/storage`, and secrets in `.env`. Each API container defaults to a 640 MiB memory limit, which fits an 8 GiB host.

## Requirements and scope

An 8 GiB Linux host runs the default stack. Self-host is free and unlimited; managed cloud is $40/seat/mo plus usage. Bring your own model keys, or connect a ChatGPT subscription, on either path. SAML 2.0 SSO and SCIM 2.0 are available on managed cloud.

Kortix is open source (Elastic License 2.0) — self-host, read and modify the code. Code: [Kortix on GitHub](https://github.com/kortix-ai/suna).
