# Open source Kortix vs Claude Cowork vs ChatGPT Work

If you are choosing where a team runs agents, the decision comes down to what you own. Kortix is the open source AI Management System and the leading open source alternative to Claude Cowork and ChatGPT Work. This page compares the three on the dimensions that decide a self-host decision: source, models, where it runs, where the configuration lives, and access. Competitor rows reflect each vendor's publicly documented behavior, checked October 2026.

## The comparison

| | Kortix | Claude Cowork | ChatGPT Work |
| --- | --- | --- | --- |
| Open source | Yes. Elastic License 2.0: read, modify, self-host. | No. Closed, proprietary, Anthropic. | No. Closed, proprietary, OpenAI. |
| Models | Any provider, your own keys. | Anthropic models only. | GPT-5.6 only. |
| Where it runs | Your cloud, VPC, on-prem, or managed. | Anthropic's cloud, or your Bedrock/Google Cloud/Microsoft Foundry. No self-host. | OpenAI's cloud. No self-host. |
| Your configuration | Files in a git repo you own. | Inside their product. | Inside their product. |
| Access | Self-host free. Managed cloud $40/seat/mo + usage. | Paid plans: Pro, Max, Team, Enterprise. | Paid plans, usage-metered. |

Kortix is open source (Elastic License 2.0) — self-host, read and modify the code.

Pick Kortix when you want the do-the-work power as a company platform: many agents across departments, any model with your keys, self-hosted, with the configuration versioned in a repo you own.

## What each difference means

### Ownership

A Kortix company is one git repo. Agents, skills, memory, connector config, and triggers are files, so a change is a diff you review, and you can roll it back. Claude Cowork and ChatGPT Work keep their configuration inside their products, so you configure through their console and you do not hold the files. The code is at [Kortix on GitHub](https://github.com/kortix-ai/suna).

### Models

Kortix runs Anthropic, OpenAI, Google, or your own OpenAI-compatible endpoint, per agent, per session, per message, with your own keys. Claude Cowork runs Anthropic models only, as documented on the [Claude Cowork product page](https://claude.com/product/cowork). ChatGPT Work runs on OpenAI's GPT-5.6, as documented for [ChatGPT for business](https://chatgpt.com/business/enterprise).

### Where it runs

Kortix self-hosts on a laptop, a VPS, your VPC, or on-prem, and it runs on managed cloud, from the same manifest. Claude Cowork runs in Anthropic's cloud or in your Bedrock, Google Cloud, or Microsoft Foundry account, with no self-host. ChatGPT Work runs in OpenAI's cloud, with no self-host. Neither closed product can run on your own hardware.

### Access

Self-host Kortix for free. Managed cloud is $40/seat/mo plus usage. Claude Cowork is included in paid Claude plans (Pro, Max, Team, Enterprise). ChatGPT Work is paid and usage-metered.
