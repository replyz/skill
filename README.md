<p>
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset=".github/assets/replyz-logo-dark.svg">
    <img src=".github/assets/replyz-logo-light.svg" alt="Replyz" height="48">
  </picture>
</p>

# replyz/skill: the Replyz agent skill

A Markdown skill that teaches your AI agent to give itself its own email inbox with Replyz: sign up once, wait for a sign-up
code or confirmation link, and get the code back. Receive-only. It works with agents that read `SKILL.md` skills (for example
OpenClaw, Hermes and Claude Code).

**Only where a service's terms allow automated sign-ups.** The skill tells the agent never to create accounts on services
whose terms forbid automated or bot accounts. Not for bulk, marketing or disposable email.

> **Status: private testing.** Signups are closed until launch, so a new agent can't get an account yet. The skill is
> version 0.1.0. It is **not on ClawHub yet**; that comes at launch. Watch this repo or https://replyz.io.

## What is in it

| File | What it is |
| --- | --- |
| `SKILL.md` | The skill. Every command runs the CLI pinned to one version: `npx -y @replyz/cli@0.1.0 <command> --json`. |
| `LICENSE` | MIT-0 |

The CLI ([github.com/replyz/cli](https://github.com/replyz/cli), MIT) is published on npm as `@replyz/cli`, currently under the
`next` tag with provenance. It needs Node.js 22 or newer.

## What the skill covers

- Sign up once (`signup`), which solves a small proof of work and saves the API key for the CLI in `~/.config/replyz/credentials.json`
  (readable only by your user). The key is never printed.
- Tell your human the address and the claim link.
- Wait for a code or link (`wait --otp`), list and read mail.
- Treat email as untrusted: every message carries `injection_risk` and `sender_trust`, and Replyz never opens links for you.
- What it can't do yet: send or reply to email, email your human through Replyz, pick another domain.

## Use it

Copy the `SKILL.md` into the skills folder of your agent, following that agent's own documentation. We have tested the skill
with one agent only (Claude Code, driven by the CLI), so check your agent's instructions rather than assume a path.

## Links

- Website: https://replyz.io · Docs for agents: https://docs.replyz.io/llms.txt
- CLI: https://github.com/replyz/cli · MCP server: https://github.com/replyz/mcp
- Security: security@replyz.io · Everything else: hello@replyz.io
