# Gamma Watermark Remover — Agent Skill (Claude Code & OpenClaw 🦞)

![Gamma Watermark Remover — remove the Made with Gamma badge from PDF & PPTX](banner.webp)

An [agent skill](SKILL.md) that lets AI coding agents remove the **"Made with Gamma"** watermark from PDF and PowerPoint (.pptx) files exported from [Gamma.app](https://gamma.app). Once installed, just ask your agent:

> *"remove the gamma watermark from deck.pdf"*

The removal is **structural and lossless** — the watermark badge and its gamma.app hyperlink are deleted as document objects; nothing is re-rendered, text stays selectable, slides stay editable. Processing is fully local.

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

## Related

- **CLI + Python library**: [gammaremover/gamma-watermark-remover](https://github.com/gammaremover/gamma-watermark-remover) ([PyPI](https://pypi.org/project/gamma-watermark-remover/))
- **Web version (no install, runs in your browser, no upload)**: [gammaremover.com](https://gammaremover.com)
- How it works: [detection logic explained](https://github.com/gammaremover/gamma-watermark-remover#how-detection-works)

## Responsible use

For cleaning export branding from **files you created or have the right to modify** — client decks, class submissions, portfolio pieces. Gamma's official watermark-free path is its [paid plan](https://gammaremover.com/en/blog/gamma-free-vs-pro-watermark/), which heavy users may genuinely prefer.

## License

MIT
