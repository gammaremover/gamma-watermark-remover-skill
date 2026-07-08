# Gamma Watermark Remover — Agent-Skill for Claude Code and OpenClaw

[![Claude Code](https://img.shields.io/badge/Claude%20Code-skill-8b3dff)](https://docs.anthropic.com/en/docs/claude-code)
[![OpenClaw](https://img.shields.io/badge/OpenClaw-skill-ff6b35)](https://github.com/gammaremover/gamma-watermark-remover-skill)
[![CLI on PyPI](https://img.shields.io/pypi/v/gamma-watermark-remover?color=8b3dff&label=CLI%20on%20PyPI)](https://pypi.org/project/gamma-watermark-remover/)
[![License: MIT](https://img.shields.io/badge/License-MIT-8b3dff.svg)](../LICENSE)
[![Web version](https://img.shields.io/badge/Web%20version-gammaremover.com-8b3dff)](https://gammaremover.com)

[English](../README.md) | [简体中文](README.zh-CN.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [Español](README.es.md) | [Français](README.fr.md) | **Deutsch** | [Português](README.pt-BR.md) | [Русский](README.ru.md) | [Türkçe](README.tr.md) | [Italiano](README.it.md) | [Bahasa Indonesia](README.id.md) | [العربية](README.ar.md) | [हिन्दी](README.hi.md)

![Gamma Watermark Remover — remove the Made with Gamma badge from PDF & PPTX](../banner.webp)

Ein [Agent-Skill](../SKILL.md), mit dem KI-Programmieragenten das **„Made with Gamma"**-Wasserzeichen aus PDF- und PowerPoint-Dateien (.pptx) entfernen können, die von [Gamma.app](https://gamma.app) exportiert wurden. Nach der Installation genügt eine einfache Anweisung an Ihren Agenten:

> *„Entferne das Gamma-Wasserzeichen aus deck.pdf"* ("remove the gamma watermark from deck.pdf")

Die Entfernung ist **strukturell und verlustfrei** — das Wasserzeichen-Badge und sein gamma.app-Hyperlink werden als Dokumentobjekte gelöscht; nichts wird neu gerendert, Text bleibt auswählbar, Folien bleiben bearbeitbar. Die Verarbeitung erfolgt vollständig lokal.

## Installation

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

Projektbezogene Installation ist ebenfalls möglich: Legen Sie die Datei in `.claude/skills/gamma-watermark-remover/` in einem beliebigen Repository ab oder im `skills/`-Verzeichnis Ihres OpenClaw-Workspace. Eine einzige `SKILL.md` — das Format ist für beide Agenten identisch.

## Was der Skill macht

1. Validiert die Datei (`.pdf` / `.pptx`, nur eigene Exporte des Benutzers)
2. Installiert das CLI bei Bedarf: [`pip install gamma-watermark-remover`](https://pypi.org/project/gamma-watermark-remover/)
3. Führt die Entfernung durch und interpretiert das Ergebnis (einschließlich des ehrlichen `may_remain`-Flags, wenn ein Badge in das Seitenbild eingebettet wurde und nicht strukturell entfernt werden kann)
4. Erinnert den Benutzer daran, die bereinigte Datei zu prüfen und das Original aufzubewahren

## Verwandte Ressourcen

- **CLI + Python-Bibliothek**: [gammaremover/gamma-watermark-remover](https://github.com/gammaremover/gamma-watermark-remover) ([PyPI](https://pypi.org/project/gamma-watermark-remover/))
- **Webversion (ohne Installation, läuft im Browser, kein Upload nötig)**: [gammaremover.com](https://gammaremover.com)
- Funktionsweise: [Erklärung der Erkennungslogik](https://github.com/gammaremover/gamma-watermark-remover#how-detection-works)

## Verantwortungsvolle Nutzung

Zum Entfernen des Export-Brandings aus **Dateien, die Sie erstellt haben oder zu deren Bearbeitung Sie berechtigt sind** — Kundenpräsentationen, Studienarbeiten, Portfolio-Stücke. Gammas offizieller Weg ohne Wasserzeichen ist der [kostenpflichtige Plan](https://gammaremover.com/en/blog/gamma-free-vs-pro-watermark/), den Vielnutzer möglicherweise bevorzugen.

## Lizenz

MIT
