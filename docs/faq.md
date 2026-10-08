# FAQ: open source Claude Cowork alternative

Five questions developers ask before running an agent team on Kortix. Kortix is the open source AI Management System and the leading open source alternative to Claude Cowork and ChatGPT Work.

## What does "open source" mean for Kortix?

Kortix is open source (Elastic License 2.0) — self-host, read and modify the code. The company configuration is open too, because agents, skills, memory, connector config, and triggers are files in one git repo you own. Read, fork, or audit the code at [Kortix on GitHub](https://github.com/kortix-ai/suna).

## Can I self-host it?

Yes. Install the CLI with `curl -fsSL https://kortix.com/install | bash`, then run `kortix self-host start` to bring up one Docker Compose stack. It runs on a laptop, a VPS, your VPC, or on-prem, and the same `kortix.yaml` runs on managed cloud. An 8 GiB Linux host fits the default stack.

## Which models can I use?

Any model, with your own keys: Anthropic, OpenAI, Google, or your own OpenAI-compatible endpoint. You set the model per agent, per session, or per message, and you can also sign in with a ChatGPT subscription. Claude Cowork runs Anthropic models only, and ChatGPT Work runs GPT-5.6 only.

## How do agents get permission to act?

Deny-by-default. Each agent's grants (connectors, secrets, skills, and Kortix permissions) are listed in `kortix.yaml`, and every connector tool call is allow, ask, or block, down to the arguments. An agent may open a change request but not merge it, so work reaches main only through a human review.

## Is there an audit trail?

Yes. Every session runs on its own isolated Linux sandbox on a branch named after the session, and only committed changes survive. Work lands as a change request a human reads as a diff, the repo records every change to an agent or a skill, and admins get an audit trail plus SAML 2.0 SSO and SCIM 2.0 on managed cloud.
