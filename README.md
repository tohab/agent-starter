# Agent Starter

A small, provider-neutral starting point for assistants that do useful work, stay grounded in the right context, and can act autonomously within clear limits.

This is a set of operating instructions and templates, not a model, a copy of Codex's internal instructions, or a way to change a model's weights. It distills practical lessons from running an assistant: understand the intended outcome before polishing, retrieve only the context a task needs, let the agent complete work already authorized, and verify what actually happened.

## Quick start

1. Copy [`AGENTS.md`](AGENTS.md) into the root of the project where your assistant works.
2. Copy [`templates/project-context.md`](templates/project-context.md) there as `AGENT_CONTEXT.md`. Fill in only useful, non-secret facts and keep the private copy out of public version control.
3. If an agent is doing the setup, have it follow [`AGENT_SETUP.md`](AGENT_SETUP.md). For manual setup, continue below.
4. If the agent will use accounts or act for you, copy [`templates/autonomy-policy.md`](templates/autonomy-policy.md) to a private `AUTONOMY_POLICY.md`. Define exact targets, action levels, limits, standing rules, exceptions, and verification before connecting tools.
5. Optionally copy [`templates/agent-role.md`](templates/agent-role.md) to a private `AGENT_ROLE.md` to define its purpose, domain, and accountabilities.
6. Follow [`docs/tool-setup.md`](docs/tool-setup.md) to connect only the capabilities the workflow needs. Check the provider's actual consent screen and permissions.
7. Keep the owner's existing task system as the source of truth. Try one allowed and one disallowed case with harmless content. Use [`templates/behavior-review.md`](templates/behavior-review.md) to record a mismatch and improve one instruction at a time.

In Codex, `AGENTS.md` is a project instruction file. Other assistants may use a different filename or setup path; follow their current documentation rather than assuming a renamed file will be loaded.

## Keep public and private material separate

This repository contains generic starter guidance. Keep your own project context, autonomy policy, chat history, decisions, credentials, customer data, and account details in the appropriate private system. Do not add them to a fork or pull request. [`docs/privacy-and-release.md`](docs/privacy-and-release.md) gives a short release check.

The written material in this repository is licensed under [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/). You may share and adapt it with attribution and a note of changes. See [`LICENSE`](LICENSE) for the license notice.

## What it helps with

- Turning a request into a clear outcome and a small next step.
- Finding the current, authoritative source without loading every old note.
- Completing routine actions autonomously when a standing rule clearly covers the action, target, audience, and limits.
- Escalating only decisions outside the grant, such as a new recipient, audience, permission, or hard-to-reverse action.
- Reporting verified changes and remaining unknowns without overstating success.
- Improving working instructions from specific feedback and repeatable examples.

## Files

- [`AGENTS.md`](AGENTS.md): copy-ready project operating instructions.
- [`templates/project-context.md`](templates/project-context.md): a private, task-focused context template.
- [`templates/agent-role.md`](templates/agent-role.md): a private role card for purpose, domain, and accountabilities.
- [`templates/autonomy-policy.md`](templates/autonomy-policy.md): a private policy template for account targets, routine rights, limits, exceptions, and verification.
- [`templates/behavior-review.md`](templates/behavior-review.md): a private review note for a concrete mismatch.
- [`templates/decision-record.md`](templates/decision-record.md): a concise record of an adopted local decision.
- [`templates/task-brief.md`](templates/task-brief.md): a bounded handoff for a delegated task, when your platform supports delegation.
- [`docs/autonomy-and-permissions.md`](docs/autonomy-and-permissions.md): defining useful, reviewable standing authority.
- [`AGENT_SETUP.md`](AGENT_SETUP.md): step-by-step setup instructions for an agent asked to configure itself.
- [`docs/tool-setup.md`](docs/tool-setup.md): connecting email, GitHub, notes, publishing, and other tools with narrow permissions.
- [`docs/improvement-loop.md`](docs/improvement-loop.md): how to turn feedback into tested instruction changes.
- [`docs/privacy-and-release.md`](docs/privacy-and-release.md): how to keep private context out of public material.
