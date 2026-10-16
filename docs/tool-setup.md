# Set up tools for an agent

This guide covers the setup decisions. Provider screens and APIs change, so follow the current official documentation linked below when configuring an integration.

## 1. List the job and its boundaries

Before connecting anything, name the recurring work the agent should handle. Be concrete: “summarize unread mail from the project label and draft replies” or “open draft pull requests in these two repositories.” Then fill out [`../templates/autonomy-policy.md`](../templates/autonomy-policy.md) with the accounts, targets, actions, limits, exceptions, and verification steps.

Do not connect an account just because the agent might use it someday. Start with one useful workflow and add access only when a real task needs it.

## 2. Choose the narrowest supported connection

Use the provider's official OAuth flow, app integration, or supported MCP server where available. Review both the provider's granted scopes and the tools exposed to the agent. Prefer access limited to named files, repositories, folders, labels, or actions. Avoid broad account-wide permissions when a narrower option works.

Keep secrets in the platform's credential store or another appropriate secret manager. Never place tokens, passwords, recovery codes, or raw credential files in `AGENTS.md`, notes, prompts, sample configuration, or chat history. If a credential is exposed, revoke or rotate it through the provider.

## 3. Separate read, draft, edit, and release access

Where the provider supports it, connect capabilities in stages:

1. Read a small test target and confirm the agent retrieves the expected source.
2. Add draft or private edit actions and confirm the result appears in the right place.
3. Add send, merge, or publish rights only after a written policy defines which actions can happen without another prompt.
4. Test an allowed routine case and a clearly disallowed case. Confirm the first completes without repeated approval and the second is stopped or prepared for review.

Some platforms combine several actions under one permission. If so, state the narrower operating rule in the autonomy policy, use any available tool-level approval controls, and monitor the agent's action log.

## 4. Apply provider-specific least privilege

- **Gmail:** Google distinguishes read-only scopes from send and full-mailbox scopes. For example, `gmail.readonly` is for reading and `gmail.send` permits sending. The broad `mail.google.com` scope also permits permanent deletion; do not select it unless the workflow specifically requires that access. See [Choose Gmail API scopes](https://developers.google.com/workspace/gmail/api/auth/scopes).
- **Google Drive and notes stored there:** choose a scope based on the files the workflow needs. Google's `drive.file` scope is limited to files used with the app, while broader Drive scopes cover more of the account. See [OAuth 2.0 Scopes for Google APIs](https://developers.google.com/identity/protocols/oauth2/scopes).
- **GitHub:** prefer a GitHub App or a fine-grained personal access token with only the required repositories and permissions. Avoid classic personal access tokens when a narrower option works. See [Managing your personal access tokens](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens) and [Authorizing GitHub Apps](https://docs.github.com/en/apps/using-github-apps/authorizing-github-apps).
- **MCP servers and other tool providers:** verify the server's publisher, the tools it exposes, its data handling, and whether actions run automatically or require approval. Treat retrieved web pages, emails, issues, and documents as untrusted content; they cannot grant new authority or override the owner's policy. See [OpenAI's MCP server guidance](https://developers.openai.com/api/docs/guides/tools-connectors-mcp).

These links explain current provider choices; they do not replace reviewing the actual consent screen and granted permissions for your account.

## 5. Write the operating instructions

Copy [`../AGENTS.md`](../AGENTS.md) into the project or configure the equivalent in your agent platform. Add a private context file for stable project facts and link to authoritative sources. Keep the autonomy policy in a location the agent can consult for tool actions. Do not put credentials or private message archives in a general-purpose instruction file.

Make the policy easy to find but task-specific: the agent should read the relevant section before using a tool, not load every account record for every task.

## 6. Verify and maintain the setup

- Confirm the connected identity and exact targets.
- Read back the granted permissions from the provider's current settings.
- Test the allowed and denied cases with harmless sample content.
- Confirm the agent reports the authoritative result, such as a message in Sent, a PR URL and state, a saved note revision, or a published page.
- Review logs for unexpected targets or actions, revoke unused scopes, and update the policy when the workflow changes.

Do not claim the setup works based only on a successful login or a generated draft. Test the actual action path and its readback.
