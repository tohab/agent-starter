# Give an agent room to act safely

An agent can work with less interruption when its standing authority is clear. The goal is not to ask for approval at every step. The goal is to define a useful scope once, let the agent complete routine work inside it, and surface only decisions outside that scope.

## Guiding models

- **Work flow:** use a GTD-inspired Capture, Clarify, Organize, Reflect, Engage loop. Put work in the owner's existing trusted task system; do not create a parallel queue.
- **Agent roles:** use a Holacracy-inspired role card with a purpose, domain, and accountabilities. A role describes the work; it does not grant account or tool permissions by itself.
- **Autonomy:** inside the owner's explicit scope, continue through the next useful steps and verify the outcome. Ask only when a real decision falls outside that scope.

These are lightweight guides, not a requirement to adopt either full methodology.

## Define the grant before connecting tools

Write down:

1. **Who owns the account and grant.** Name the person or team that can authorize actions and revoke access.
2. **Which targets are included.** Specify email accounts, labels or folders, GitHub organizations and repositories, note spaces, sites, and audiences. Avoid phrases such as “all my accounts” when you can name the actual target.
3. **Which action levels are allowed.** Reading, preparing drafts, editing private content, sending or merging, and publishing are different rights. Grant only the levels needed.
4. **What limits apply.** Define recipients, content types, frequency or quantity limits, release windows, spend limits, and actions that are always excluded.
5. **How the agent verifies and reports.** Identify the authoritative readback (sent folder, PR state, note revision, published URL), what to log, and how to undo or contain a mistake.

Record access and standing grants in [`../templates/autonomy-policy.md`](../templates/autonomy-policy.md). Describe an agent's purpose and responsibilities in [`../templates/agent-role.md`](../templates/agent-role.md). A role can focus work, but it does not replace the owner's permission grant.

## Use action levels, not one broad “full access” switch

| Area | Useful routine autonomy | Rights to scope separately |
| --- | --- | --- |
| Email | Find and summarize messages in named folders; label or archive within a rule; draft replies; send routine replies to a defined audience using agreed content rules | Sending to new recipients, forwarding attachments, responding on sensitive topics, deleting permanently, changing filters or account security |
| GitHub | Read selected repositories; create branches; make changes; open or update draft pull requests; summarize issues | Merge, release, change permissions, publish packages, delete branches or repositories, act in other organizations |
| Notes | Search named spaces; create or edit notes in an agreed area; maintain indexes and summaries | Share notes, alter access, delete records, move private material into a public space |
| Publishing | Prepare and preview changes; publish routine updates to a named site or account when a written release rule covers them | New channels or audiences, legal or financial claims, announcements, irreversible releases, changing domains or account access |

This table is a prompt for policy decisions, not a default permission grant. Choose each capability for the specific account and tool.

## A practical autonomy ladder

- **Read:** retrieve only the named sources needed for the task.
- **Prepare:** create drafts, branches, previews, or proposed edits without sending or releasing them.
- **Maintain:** make reversible changes in a named private workspace, with readback and recovery available.
- **Act under a standing rule:** send, merge, or publish a repeatable class of work to a specified target and audience, within explicit content and rate limits.
- **Exceptional action:** stop for a decision when the action is outside the rule, crosses into a new audience or account, has unclear consequences, or is difficult to undo.

An owner can authorize any appropriate level. For example, a trusted agent may send routine scheduling replies to known participants without asking each time, while still escalating a new recipient or a message that makes a commitment. A blanket request to “handle email” does not define those boundaries by itself.

## Keep the permission layers separate

Use three checks:

1. **Tool capability:** can the connected integration technically perform the action?
2. **User authority:** has the account owner allowed this agent to perform this kind of action on this target?
3. **Task fit:** does the current request or standing rule cover this particular action and its audience?

All three must allow the action. A narrow provider permission reduces the possible damage if something goes wrong; the written policy narrows what the agent should do. Neither replaces the other.

## Keep autonomy reviewable

- Use specific scopes, named repositories and spaces, and separate read, draft, edit, send, merge, and publish rights where the provider supports them.
- Prefer a preview, draft, branch, or reversible update before a release when the workflow allows it.
- For actions covered by a standing rule, proceed without a per-action confirmation. Report what happened and link to the result.
- Before a consequential action, check the target, audience, content, and limits against the policy. Escalate only the missing decision, not the whole task.
- Read the resulting state back from the authoritative service. “Tool call succeeded” is not enough to prove delivery, merge, or publication.
- Keep an action log that records the target, action, time, result, and relevant rule. Do not copy entire messages or private content into a public log.
- Give the owner a clear way to pause or revoke the integration. Review scopes when the job changes and periodically while it remains active.
