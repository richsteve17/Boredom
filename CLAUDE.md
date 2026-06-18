# CLAUDE.md

Guidance for Claude Code working in this repository.

## Purpose

This repo is a workspace pre-wired with the
[`claude-skills`](https://github.com/alirezarezvani/claude-skills) plugin
marketplace. Its real content is the Claude Code configuration, not application
code.

## Configuration

`.claude/settings.json` registers one marketplace and enables all of its plugins:

- `extraKnownMarketplaces.claude-code-skills` → source `github:alirezarezvani/claude-skills`
- `enabledPlugins` → all 78 plugins, each keyed as `"<name>@claude-code-skills": true`

When the user trusts this folder, every skill, agent, and persona from the
marketplace becomes available with no manual install step.

## How the user invokes capabilities

- **Skills** — auto-loaded when relevant to the user's request, or invoked
  explicitly as `/<skill-name>`. Prefer loading a matching skill over answering
  from scratch when one clearly fits the task.
- **Agents** — subagents for multi-step jobs; launch via the Agent/Task tool
  when the user asks to "use the X agent" or when a task matches one.
- **Personas / advisors** — skills that set a voice/role (e.g. `andreessen`,
  `karpathy-coder`, `*-advisor`). Invoke like any other skill.

When the user asks "what skills/agents/personas do I have" or "how do I use
one," point them to:
- `/plugin` — browse and toggle plugins in the `claude-code-skills` marketplace
- `/help` or typing `/` — list every available slash command/skill
- the marketplace repo's `.claude-plugin/marketplace.json` — source of truth for
  plugin names

## Editing the plugin set

To enable/disable plugins, edit `enabledPlugins` in `.claude/settings.json`
(set to `false` or remove the line) or use `/plugin` interactively. Keep names
in `<plugin-name>@claude-code-skills` form. If adding plugins, verify the exact
`name` against the marketplace's `marketplace.json` first — some intuitive names
differ (the Playwright plugin is `pw`; there is no `playwright-pro`,
`skill-security-auditor`, or `content-creator`).
