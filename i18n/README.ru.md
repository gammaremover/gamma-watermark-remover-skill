# Gamma Watermark Remover — навык агента for Claude Code and OpenClaw

[![Claude Code](https://img.shields.io/badge/Claude%20Code-skill-8b3dff)](https://docs.anthropic.com/en/docs/claude-code)
[![OpenClaw](https://img.shields.io/badge/OpenClaw-skill-ff6b35)](https://github.com/gammaremover/gamma-watermark-remover-skill)
[![CLI on PyPI](https://img.shields.io/pypi/v/gamma-watermark-remover?color=8b3dff&label=CLI%20on%20PyPI)](https://pypi.org/project/gamma-watermark-remover/)
[![License: MIT](https://img.shields.io/badge/License-MIT-8b3dff.svg)](../LICENSE)
[![Web version](https://img.shields.io/badge/Web%20version-gammaremover.com-8b3dff)](https://gammaremover.com)

[English](../README.md) | [简体中文](README.zh-CN.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [Español](README.es.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [Português](README.pt-BR.md) | **Русский** | [Türkçe](README.tr.md) | [Italiano](README.it.md) | [Bahasa Indonesia](README.id.md) | [العربية](README.ar.md) | [हिन्दी](README.hi.md)

![Gamma Watermark Remover — remove the Made with Gamma badge from PDF & PPTX](../banner.webp)

[Навык агента](../SKILL.md), который позволяет ИИ-агентам программирования удалять водяной знак **«Made with Gamma»** из PDF- и PowerPoint-файлов (.pptx), экспортированных из [Gamma.app](https://gamma.app). После установки просто попросите своего агента:

> *«удали водяной знак Gamma из deck.pdf»* ("remove the gamma watermark from deck.pdf")

Удаление **структурное и без потерь** — значок водяного знака и его гиперссылка на gamma.app удаляются как объекты документа; ничего не перерисовывается, текст остаётся выделяемым, слайды остаются редактируемыми. Обработка полностью локальная.

## Установка

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

Установка на уровне проекта тоже работает: поместите файл в `.claude/skills/gamma-watermark-remover/` внутри любого репозитория или в директорию `skills/` вашего рабочего пространства OpenClaw. Один `SKILL.md` — формат идентичен для обоих агентов.

## Что делает навык

1. Проверяет файл (`.pdf` / `.pptx`, только собственные экспорты пользователя)
2. Устанавливает CLI по запросу: [`pip install gamma-watermark-remover`](https://pypi.org/project/gamma-watermark-remover/)
3. Выполняет удаление и интерпретирует результат (включая честный флаг `may_remain`, если значок был растеризован в изображение страницы и не может быть удалён структурно)
4. Напоминает пользователю проверить очищенный файл и сохранить оригинал

## Связанные ресурсы

- **CLI + библиотека Python**: [gammaremover/gamma-watermark-remover](https://github.com/gammaremover/gamma-watermark-remover) ([PyPI](https://pypi.org/project/gamma-watermark-remover/))
- **Веб-версия (без установки, работает в браузере, без загрузки файлов)**: [gammaremover.com](https://gammaremover.com)
- Как это работает: [описание логики обнаружения](https://github.com/gammaremover/gamma-watermark-remover#how-detection-works)

## Ответственное использование

Для удаления экспортного брендинга из **файлов, которые вы создали или имеете право изменять** — клиентские презентации, учебные работы, портфолио. Официальный способ убрать водяной знак от Gamma — [платный план](https://gammaremover.com/en/blog/gamma-free-vs-pro-watermark/), который активным пользователям может действительно подойти больше.

## Лицензия

MIT
