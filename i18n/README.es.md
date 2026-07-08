# Gamma Watermark Remover — Skill de agente for Claude Code and OpenClaw

[![Claude Code](https://img.shields.io/badge/Claude%20Code-skill-8b3dff)](https://docs.anthropic.com/en/docs/claude-code)
[![OpenClaw](https://img.shields.io/badge/OpenClaw-skill-ff6b35)](https://github.com/gammaremover/gamma-watermark-remover-skill)
[![CLI on PyPI](https://img.shields.io/pypi/v/gamma-watermark-remover?color=8b3dff&label=CLI%20on%20PyPI)](https://pypi.org/project/gamma-watermark-remover/)
[![License: MIT](https://img.shields.io/badge/License-MIT-8b3dff.svg)](../LICENSE)
[![Web version](https://img.shields.io/badge/Web%20version-gammaremover.com-8b3dff)](https://gammaremover.com)

[English](../README.md) | [简体中文](README.zh-CN.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | **Español** | [Français](README.fr.md) | [Deutsch](README.de.md) | [Português](README.pt-BR.md) | [Русский](README.ru.md) | [Türkçe](README.tr.md) | [Italiano](README.it.md) | [Bahasa Indonesia](README.id.md) | [العربية](README.ar.md) | [हिन्दी](README.hi.md)

![Gamma Watermark Remover — remove the Made with Gamma badge from PDF & PPTX](../banner.webp)

Un [skill de agente](../SKILL.md) que permite a los agentes de programación con IA eliminar la marca de agua **"Made with Gamma"** de archivos PDF y PowerPoint (.pptx) exportados desde [Gamma.app](https://gamma.app). Una vez instalado, solo pídele a tu agente:

> *"elimina la marca de agua de Gamma de deck.pdf"* ("remove the gamma watermark from deck.pdf")

La eliminación es **estructural y sin pérdidas** — el badge de marca de agua y su hipervínculo a gamma.app se eliminan como objetos del documento; nada se vuelve a renderizar, el texto sigue siendo seleccionable y las diapositivas siguen siendo editables. El procesamiento es completamente local.

## Instalación

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

También se puede instalar a nivel de proyecto: coloca el archivo en `.claude/skills/gamma-watermark-remover/` dentro de cualquier repositorio, o en el directorio `skills/` de tu workspace de OpenClaw. Un solo `SKILL.md` — el formato es idéntico para ambos agentes.

## Qué hace el skill

1. Valida el archivo (`.pdf` / `.pptx`, solo exportaciones propias del usuario)
2. Instala el CLI bajo demanda: [`pip install gamma-watermark-remover`](https://pypi.org/project/gamma-watermark-remover/)
3. Ejecuta la eliminación e interpreta el resultado (incluyendo la bandera honesta `may_remain` cuando el badge fue aplanado en la imagen de la página y no puede eliminarse estructuralmente)
4. Recuerda al usuario revisar el archivo limpio y conservar el original

## Recursos relacionados

- **CLI + librería Python**: [gammaremover/gamma-watermark-remover](https://github.com/gammaremover/gamma-watermark-remover) ([PyPI](https://pypi.org/project/gamma-watermark-remover/))
- **Versión web (sin instalación, funciona en tu navegador, sin subida de archivos)**: [gammaremover.com](https://gammaremover.com)
- Cómo funciona: [explicación de la lógica de detección](https://github.com/gammaremover/gamma-watermark-remover#how-detection-works)

## Uso responsable

Para limpiar la marca de exportación de **archivos que tú creaste o tienes derecho a modificar** — presentaciones para clientes, trabajos de clase, piezas de portafolio. La vía oficial de Gamma para eliminar la marca de agua es su [plan de pago](https://gammaremover.com/en/blog/gamma-free-vs-pro-watermark/), que los usuarios frecuentes podrían preferir genuinamente.

## Licencia

MIT
