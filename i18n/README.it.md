# Gamma Watermark Remover — Skill per agente for Claude Code and OpenClaw

[![Claude Code](https://img.shields.io/badge/Claude%20Code-skill-8b3dff)](https://docs.anthropic.com/en/docs/claude-code)
[![OpenClaw](https://img.shields.io/badge/OpenClaw-skill-ff6b35)](https://github.com/gammaremover/gamma-watermark-remover-skill)
[![CLI on PyPI](https://img.shields.io/pypi/v/gamma-watermark-remover?color=8b3dff&label=CLI%20on%20PyPI)](https://pypi.org/project/gamma-watermark-remover/)
[![License: MIT](https://img.shields.io/badge/License-MIT-8b3dff.svg)](../LICENSE)
[![Web version](https://img.shields.io/badge/Web%20version-gammaremover.com-8b3dff)](https://gammaremover.com)

[English](../README.md) | [简体中文](README.zh-CN.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [Español](README.es.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [Português](README.pt-BR.md) | [Русский](README.ru.md) | [Türkçe](README.tr.md) | **Italiano** | [Bahasa Indonesia](README.id.md) | [العربية](README.ar.md) | [हिन्दी](README.hi.md)

![Gamma Watermark Remover — remove the Made with Gamma badge from PDF & PPTX](../banner.webp)

Uno [skill per agente](../SKILL.md) che permette agli agenti di programmazione IA di rimuovere la filigrana **"Made with Gamma"** dai file PDF e PowerPoint (.pptx) esportati da [Gamma.app](https://gamma.app). Una volta installato, basta chiedere al tuo agente:

> *"rimuovi la filigrana Gamma da deck.pdf"* ("remove the gamma watermark from deck.pdf")

La rimozione è **strutturale e senza perdite** — il badge della filigrana e il suo collegamento ipertestuale a gamma.app vengono eliminati come oggetti del documento; nulla viene ri-renderizzato, il testo resta selezionabile e le slide restano modificabili. L'elaborazione avviene interamente in locale.

## Installazione

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

Funziona anche l'installazione a livello di progetto: inserisci il file in `.claude/skills/gamma-watermark-remover/` all'interno di qualsiasi repository, o nella directory `skills/` del tuo workspace OpenClaw. Un unico `SKILL.md` — il formato è identico per entrambi gli agenti.

## Cosa fa lo skill

1. Valida il file (`.pdf` / `.pptx`, solo esportazioni dell'utente)
2. Installa il CLI su richiesta: [`pip install gamma-watermark-remover`](https://pypi.org/project/gamma-watermark-remover/)
3. Esegue la rimozione e interpreta il risultato (incluso il flag onesto `may_remain` quando il badge è stato appiattito nell'immagine della pagina e non può essere rimosso strutturalmente)
4. Ricorda all'utente di verificare il file pulito e conservare l'originale

## Risorse correlate

- **CLI + libreria Python**: [gammaremover/gamma-watermark-remover](https://github.com/gammaremover/gamma-watermark-remover) ([PyPI](https://pypi.org/project/gamma-watermark-remover/))
- **Versione web (senza installazione, funziona nel browser, senza upload)**: [gammaremover.com](https://gammaremover.com)
- Come funziona: [spiegazione della logica di rilevamento](https://github.com/gammaremover/gamma-watermark-remover#how-detection-works)

## Uso responsabile

Per rimuovere il branding di esportazione da **file che hai creato o che hai il diritto di modificare** — presentazioni per clienti, lavori scolastici, pezzi di portfolio. Il percorso ufficiale di Gamma senza filigrana è il [piano a pagamento](https://gammaremover.com/en/blog/gamma-free-vs-pro-watermark/), che gli utenti assidui potrebbero genuinamente preferire.

## Licenza

MIT
