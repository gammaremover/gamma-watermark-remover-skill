# Gamma Watermark Remover — Compétence d'agent for Claude Code and OpenClaw

[![Claude Code](https://img.shields.io/badge/Claude%20Code-skill-8b3dff)](https://docs.anthropic.com/en/docs/claude-code)
[![OpenClaw](https://img.shields.io/badge/OpenClaw-skill-ff6b35)](https://github.com/gammaremover/gamma-watermark-remover-skill)
[![CLI on PyPI](https://img.shields.io/pypi/v/gamma-watermark-remover?color=8b3dff&label=CLI%20on%20PyPI)](https://pypi.org/project/gamma-watermark-remover/)
[![License: MIT](https://img.shields.io/badge/License-MIT-8b3dff.svg)](../LICENSE)
[![Web version](https://img.shields.io/badge/Web%20version-gammaremover.com-8b3dff)](https://gammaremover.com)

[English](../README.md) | [简体中文](README.zh-CN.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [Español](README.es.md) | **Français** | [Deutsch](README.de.md) | [Português](README.pt-BR.md) | [Русский](README.ru.md) | [Türkçe](README.tr.md) | [Italiano](README.it.md) | [Bahasa Indonesia](README.id.md) | [العربية](README.ar.md) | [हिन्दी](README.hi.md)

![Gamma Watermark Remover — remove the Made with Gamma badge from PDF & PPTX](../banner.webp)

Une [compétence d'agent](../SKILL.md) qui permet aux agents de programmation IA de supprimer le filigrane **« Made with Gamma »** des fichiers PDF et PowerPoint (.pptx) exportés depuis [Gamma.app](https://gamma.app). Une fois installée, demandez simplement à votre agent :

> *« supprime le filigrane Gamma de deck.pdf »* ("remove the gamma watermark from deck.pdf")

La suppression est **structurelle et sans perte** — le badge de filigrane et son lien hypertexte vers gamma.app sont supprimés en tant qu'objets du document ; rien n'est re-rendu, le texte reste sélectionnable et les diapositives restent modifiables. Le traitement est entièrement local.

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

L'installation au niveau du projet fonctionne aussi : déposez le fichier dans `.claude/skills/gamma-watermark-remover/` dans n'importe quel dépôt, ou dans le répertoire `skills/` de votre espace de travail OpenClaw. Un seul `SKILL.md` — le format est identique pour les deux agents.

## Ce que fait la compétence

1. Valide le fichier (`.pdf` / `.pptx`, uniquement les exportations de l'utilisateur)
2. Installe le CLI à la demande : [`pip install gamma-watermark-remover`](https://pypi.org/project/gamma-watermark-remover/)
3. Exécute la suppression et interprète le résultat (y compris le drapeau honnête `may_remain` lorsqu'un badge a été aplati dans l'image de la page et ne peut pas être supprimé structurellement)
4. Rappelle à l'utilisateur de vérifier le fichier nettoyé et de conserver l'original

## Ressources associées

- **CLI + bibliothèque Python** : [gammaremover/gamma-watermark-remover](https://github.com/gammaremover/gamma-watermark-remover) ([PyPI](https://pypi.org/project/gamma-watermark-remover/))
- **Version web (sans installation, fonctionne dans votre navigateur, sans téléversement)** : [gammaremover.com](https://gammaremover.com)
- Fonctionnement : [explication de la logique de détection](https://github.com/gammaremover/gamma-watermark-remover#how-detection-works)

## Utilisation responsable

Pour nettoyer le branding d'exportation de **fichiers que vous avez créés ou que vous avez le droit de modifier** — présentations clients, travaux scolaires, pièces de portfolio. La solution officielle de Gamma pour supprimer le filigrane est son [plan payant](https://gammaremover.com/en/blog/gamma-free-vs-pro-watermark/), que les utilisateurs intensifs pourraient préférer.

## Licence

MIT
