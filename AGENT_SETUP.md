# Agent setup instructions

Use this checklist when the owner asks you to set up an agent with this starter. Follow the steps in order. Do not connect an account, grant yourself access, or enable sending or publishing unless the owner has authorized the specific scope.

1. **Confirm the job.** Identify the owner, intended outcome, first workflow, and task system already in use. If a missing answer would change the scope, ask one bundled question. Do not create a second task queue.
2. **Install the instructions.** Copy `AGENTS.md` to the project root or configure its equivalent in the agent platform. Link the relevant canonical sources and keep instructions short.
3. **Create private context.** Add the ignore rules for `AGENT_CONTEXT.md`, `AGENT_ROLE.md`, and `AUTONOMY_POLICY.md` to the project's `.gitignore`. Copy `templates/project-context.md` to `AGENT_CONTEXT.md` and fill only durable facts the agent needs.
4. **Define role and authority.** Copy `templates/agent-role.md` to `AGENT_ROLE.md`. If tools or external actions are involved, copy `templates/autonomy-policy.md` to `AUTONOMY_POLICY.md`. The owner sets targets, rights, limits, and escalation rules; leave unknown rights ungranted.
5. **Connect tools narrowly.** Follow `docs/tool-setup.md`. Use official connections and the smallest useful scopes. Do not put credentials in context, prompts, or repository files.
6. **Test the boundaries.** With harmless content, verify a read, a draft, and a reversible edit. Check that an allowed routine case proceeds without repeated approval and an out-of-scope case stops for review.
7. **Work autonomously within scope.** Use the owner's task system: Capture incoming work, Clarify the outcome and next action, Organize it there, Reflect on open work during review, and Engage by doing the next authorized step. Continue through verification without asking for each routine action.
8. **Report setup.** State which sources and tools were connected, the permissions actually granted, what was tested, and what needs an owner decision. Do not claim a connection or action works without reading back its result.

## Guiding role format

Use `templates/agent-role.md` for a concise role definition inspired by purpose, domain, and accountabilities. Treat the role as a work description, not as an access token: actual tool permissions and owner authorization remain separate.
