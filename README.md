# Gamma Watermark Remover — Agent Skill for Claude Code and OpenClaw

[![Claude Code](https://img.shields.io/badge/Claude%20Code-skill-8b3dff)](https://docs.anthropic.com/en/docs/claude-code)
[![OpenClaw](https://img.shields.io/badge/OpenClaw-skill-ff6b35)](https://github.com/gammaremover/gamma-watermark-remover-skill)
[![CLI on PyPI](https://img.shields.io/pypi/v/gamma-watermark-remover?color=8b3dff&label=CLI%20on%20PyPI)](https://pypi.org/project/gamma-watermark-remover/)
[![License: MIT](https://img.shields.io/badge/License-MIT-8b3dff.svg)](LICENSE)
[![Web version](https://img.shields.io/badge/Web%20version-gammaremover.com-8b3dff)](https://gammaremover.com)

**English** | [简体中文](i18n/README.zh-CN.md) | [日本語](i18n/README.ja.md) | [한국어](i18n/README.ko.md) | [Español](i18n/README.es.md) | [Français](i18n/README.fr.md) | [Deutsch](i18n/README.de.md) | [Português](i18n/README.pt-BR.md) | [Русский](i18n/README.ru.md) | [Türkçe](i18n/README.tr.md) | [Italiano](i18n/README.it.md) | [Bahasa Indonesia](i18n/README.id.md) | [العربية](i18n/README.ar.md) | [हिन्दी](i18n/README.hi.md)

![Gamma Watermark Remover — remove the Made with Gamma badge from PDF & PPTX](banner.webp)

An [agent skill](SKILL.md) that lets AI coding agents remove the **"Made with Gamma"** watermark from PDF and PowerPoint (.pptx) files exported from [Gamma.app](https://gamma.app). Once installed, just ask your agent:

> *"remove the gamma watermark from deck.pdf"*

The removal is **structural and lossless** — the watermark badge and its gamma.app hyperlink are deleted as document objects; nothing is re-rendered, text stays selectable, slides stay editable. Processing is fully local.

## What is this skill?

This is an agent skill — a markdown instruction file that teaches AI coding agents how to remove the "Made with Gamma" watermark from Gamma.app exports. Once the skill is installed, Claude Code and OpenClaw recognize requests like "remove the gamma watermark from deck.pdf", install the [gamma-watermark-remover CLI](https://github.com/gammaremover/gamma-watermark-remover) on demand, run the removal, interpret the result, and remind you to review the cleaned file. Everything happens locally on your machine.

The same `SKILL.md` file works in both agents because OpenClaw adopted the Claude Code skill format. There is nothing to compile and no service to sign up for — the skill is a single readable file you can audit before installing.

## Example prompts

Once installed, all of these just work:

- "remove the gamma watermark from ~/Downloads/pitch.pdf"
- "clean the Made with Gamma badge from every pptx in ./exports"
- "this deck has a gamma.app watermark — get rid of it and keep the original"

## Install

**Claude Code**

```bash
mkdir -p ~/.claude/skills/gamma-watermark-remover
curl -fsSL https://raw.githubusercontent.com/gammaremover/gamma-watermark-remover-skill/main/SKILL.md \
  -o ~/.claude/skills/gamma-watermark-remover/SKILL.md
```

**OpenClaw**

```bash
mkdir -p ~/.openclaw/skills/gamma-watermark-remover
curl -fsSL https://raw.githubusercontent.com/gammaremover/gamma-watermark-remover-skill/main/SKILL.md \
  -o ~/.openclaw/skills/gamma-watermark-remover/SKILL.md
```

Project-scoped installs work too: drop the file into `.claude/skills/gamma-watermark-remover/` inside any repo, or your OpenClaw workspace `skills/` directory. One `SKILL.md` — the format is identical for both agents.

## What the skill does

1. Validates the file (`.pdf` / `.pptx`, user-owned exports only)
2. Installs the CLI on demand: [`pip install gamma-watermark-remover`](https://pypi.org/project/gamma-watermark-remover/)
3. Runs the removal and interprets the result (including the honest `may_remain` flag when a badge was flattened into the page image and cannot be removed structurally)
4. Reminds the user to review the cleaned file and keep the original

## FAQ

**Which agents support this skill?**
Claude Code and OpenClaw natively; any agent that reads Claude-format `SKILL.md` files will also pick it up.

**Does the skill upload my files anywhere?**
No. It drives the local CLI (`pipx install gamma-watermark-remover`), so files never leave your machine. If Python is unavailable, the skill points to [gammaremover.com](https://gammaremover.com), which processes files inside your browser without uploading either.

**What formats does it handle?**
PDF and PowerPoint (.pptx) exports from Gamma.app. Removal is structural and lossless.

**What if the watermark cannot be removed?**
The CLI reports when a badge was flattened into the page image; the skill instructs the agent to relay that honestly rather than retrying destructive workarounds.

## Related Tools

- **Web app** (browser-based, no upload): [gammaremover.com](https://gammaremover.com)
- **CLI + Python library**: [gamma-watermark-remover](https://github.com/gammaremover/gamma-watermark-remover)
- **Local web UI**: [gamma-watermark-remover-webui](https://github.com/gammaremover/gamma-watermark-remover-webui)
- **MCP server** for Claude and AI agents: [gamma-watermark-remover-mcp](https://github.com/gammaremover/gamma-watermark-remover-mcp)
- **Agent skill** for Claude Code and OpenClaw: [gamma-watermark-remover-skill](https://github.com/gammaremover/gamma-watermark-remover-skill)
- **Curated Gamma resources**: [awesome-gamma](https://github.com/gammaremover/awesome-gamma)

## Responsible use

For cleaning export branding from **files you created or have the right to modify** — client decks, class submissions, portfolio pieces. Gamma's official watermark-free path is its [paid plan](https://gammaremover.com/en/blog/gamma-free-vs-pro-watermark/), which heavy users may genuinely prefer.

## License

MIT
