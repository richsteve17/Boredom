# Boredom

A workspace wired up with the [`claude-skills`](https://github.com/alirezarezvani/claude-skills)
plugin marketplace — 78 plugins bundling agents, slash commands, and skills for
Claude Code.

## What's set up here

`.claude/settings.json` does two things automatically for anyone who opens this
repo in Claude Code and trusts the folder:

1. **Registers the marketplace** `claude-code-skills`
   (source: `github:alirezarezvani/claude-skills`).
2. **Enables all 78 plugins** so every skill, agent, and persona is available
   the moment the project is trusted — no manual install step.

You don't need to run any `/plugin install` commands; trusting the folder is
enough. (If you want this on a machine *outside* this repo, run
`/plugin marketplace add alirezarezvani/claude-skills` and install what you
want.)

## The three things you can invoke

| Type | What it is | How to use it |
| --- | --- | --- |
| **Skill** | A focused capability + instructions Claude loads on demand (e.g. `a11y-audit`, `terraform-patterns`). | Type `/` to see the slash-command menu and pick one, or just describe the task — Claude auto-loads a matching skill based on its description. You can also force one with `/<skill-name>`. |
| **Agent** | A subagent with its own tools and scope that runs a multi-step job (e.g. `autoresearch-agent`, `research-orchestrator`, `c-level-agents`). | Ask Claude to "use the X agent" for the task, or invoke it from the agent picker. Claude can also delegate to one automatically. |
| **Persona / advisor** | A skill that makes Claude answer *as* a specific role or person (e.g. `andreessen`, `karpathy-coder`, `vpe-advisor`, `chief-ai-officer-advisor`). | Invoke like any skill — `/<name>` or ask Claude to "answer as <persona>". |

## How to find the full list

The authoritative, always-current list lives **inside Claude Code**, not in this
file:

- **`/plugin`** → opens the plugin manager. Browse the `claude-code-skills`
  marketplace, see every plugin, and toggle them on/off.
- **`/help`** or typing **`/`** → shows all slash commands currently available,
  including every skill these plugins add.
- **Ask Claude** → "what skills/agents do I have available?" and it will list
  what's loaded.
- **The marketplace repo** →
  [alirezarezvani/claude-skills](https://github.com/alirezarezvani/claude-skills)
  has the catalog and per-plugin docs. The `.claude-plugin/marketplace.json`
  file is the source of truth for plugin names.

## Domains at a glance

The 78 plugins span (representative examples in parentheses):

- **Engineering** — core + advanced dev, infra & SRE
  (`engineering-skills`, `engineering-advanced-skills`, `docker-development`,
  `terraform-patterns`, `kubernetes-operator`, `slo-architect`, `chaos-engineering`)
- **Product & PM** (`product-skills`, `pm-skills`, `agile-product-owner`, `code-to-prd`)
- **Marketing, growth & commercial** (`marketing-skills`, `business-growth-skills`,
  `commercial-skills`, `aeo`, `landing`, `video-content-strategist`, `youtube-full`)
- **C-level advisory & personas** (`c-level-skills`, `c-level-agents`,
  `vpe-advisor`, `chief-ai-officer-advisor`, `executive-mentor`, `andreessen`)
- **Compliance, RA/QM & governance** (`ra-qm-skills`, `compliance-os`,
  `compliance-team-eu-ai-act`, `compliance-team-iso42001`, `security-guidance`,
  `prompt-governance`)
- **Finance & business ops** (`finance-skills`, `business-operations-skills`,
  `business-investment-advisor`)
- **Research** (`autoresearch-agent`, `research-orchestrator`, `litreview`,
  `grants`, `patent`, `notebooklm`, `statistical-analyst`)
- **Productivity & meta** (`self-improving-agent`, `workflow-builder`,
  `write-a-skill`, `email-pair`, `google-workspace-cli`, `pw` (Playwright))

> Naming notes from the original setup request: the Playwright plugin is named
> **`pw`** (not `playwright-pro`), and `skill-security-auditor` /
> `content-creator` aren't in this marketplace — the closest security plugin is
> **`security-guidance`**.

## Managing what's enabled

- Turn things on/off interactively with **`/plugin`**.
- Or edit `enabledPlugins` in `.claude/settings.json` (set a plugin to `false`
  or remove its line to disable it). The key format is
  `"<plugin-name>@claude-code-skills": true`.
