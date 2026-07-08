# Gamma Watermark Remover — Skill de agente (Claude Code & OpenClaw 🦞)

[![Claude Code](https://img.shields.io/badge/Claude%20Code-skill-8b3dff)](https://docs.anthropic.com/en/docs/claude-code)
[![OpenClaw](https://img.shields.io/badge/OpenClaw-🦞%20skill-ff6b35)](https://github.com/gammaremover/gamma-watermark-remover-skill)
[![CLI on PyPI](https://img.shields.io/pypi/v/gamma-watermark-remover?color=8b3dff&label=CLI%20on%20PyPI)](https://pypi.org/project/gamma-watermark-remover/)
[![License: MIT](https://img.shields.io/badge/License-MIT-8b3dff.svg)](LICENSE)
[![Web version](https://img.shields.io/badge/🌐%20Web%20version-gammaremover.com-8b3dff)](https://gammaremover.com)

[English](README.md) | [简体中文](README.zh-CN.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [Español](README.es.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | **Português** | [Русский](README.ru.md) | [Türkçe](README.tr.md) | [Italiano](README.it.md) | [Bahasa Indonesia](README.id.md) | [العربية](README.ar.md) | [हिन्दी](README.hi.md)

![Gamma Watermark Remover — remove the Made with Gamma badge from PDF & PPTX](banner.webp)

Um [skill de agente](SKILL.md) que permite que agentes de programação com IA removam a marca d'água **"Made with Gamma"** de arquivos PDF e PowerPoint (.pptx) exportados do [Gamma.app](https://gamma.app). Após a instalação, basta pedir ao seu agente:

> *"remova a marca d'água do Gamma do deck.pdf"* ("remove the gamma watermark from deck.pdf")

A remoção é **estrutural e sem perdas** — o badge da marca d'água e seu hiperlink para gamma.app são excluídos como objetos do documento; nada é re-renderizado, o texto continua selecionável e os slides continuam editáveis. O processamento é totalmente local.

## Instalação

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

Instalações no escopo do projeto também funcionam: coloque o arquivo em `.claude/skills/gamma-watermark-remover/` dentro de qualquer repositório, ou no diretório `skills/` do seu workspace OpenClaw. Um único `SKILL.md` — o formato é idêntico para ambos os agentes.

## O que o skill faz

1. Valida o arquivo (`.pdf` / `.pptx`, apenas exportações do próprio usuário)
2. Instala o CLI sob demanda: [`pip install gamma-watermark-remover`](https://pypi.org/project/gamma-watermark-remover/)
3. Executa a remoção e interpreta o resultado (incluindo a flag honesta `may_remain` quando o badge foi achatado na imagem da página e não pode ser removido estruturalmente)
4. Lembra o usuário de revisar o arquivo limpo e manter o original

## Recursos relacionados

- **CLI + biblioteca Python**: [gammaremover/gamma-watermark-remover](https://github.com/gammaremover/gamma-watermark-remover) ([PyPI](https://pypi.org/project/gamma-watermark-remover/))
- **Versão web (sem instalação, roda no navegador, sem upload)**: [gammaremover.com](https://gammaremover.com)
- Como funciona: [explicação da lógica de detecção](https://github.com/gammaremover/gamma-watermark-remover#how-detection-works)

## Uso responsável

Para limpar a marca de exportação de **arquivos que você criou ou tem o direito de modificar** — apresentações para clientes, trabalhos acadêmicos, peças de portfólio. O caminho oficial do Gamma sem marca d'água é seu [plano pago](https://gammaremover.com/en/blog/gamma-free-vs-pro-watermark/), que usuários frequentes podem genuinamente preferir.

## Licença

MIT
