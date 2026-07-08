# Gamma 水印移除器 — Agent 技能 (Claude Code & OpenClaw 🦞)

[![Claude Code](https://img.shields.io/badge/Claude%20Code-skill-8b3dff)](https://docs.anthropic.com/en/docs/claude-code)
[![OpenClaw](https://img.shields.io/badge/OpenClaw-🦞%20skill-ff6b35)](https://github.com/gammaremover/gamma-watermark-remover-skill)
[![CLI on PyPI](https://img.shields.io/pypi/v/gamma-watermark-remover?color=8b3dff&label=CLI%20on%20PyPI)](https://pypi.org/project/gamma-watermark-remover/)
[![License: MIT](https://img.shields.io/badge/License-MIT-8b3dff.svg)](LICENSE)
[![Web version](https://img.shields.io/badge/🌐%20Web%20version-gammaremover.com-8b3dff)](https://gammaremover.com)

[English](README.md) | **简体中文** | [日本語](README.ja.md) | [한국어](README.ko.md) | [Español](README.es.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [Português](README.pt-BR.md) | [Русский](README.ru.md) | [Türkçe](README.tr.md) | [Italiano](README.it.md) | [Bahasa Indonesia](README.id.md) | [العربية](README.ar.md) | [हिन्दी](README.hi.md)

![Gamma Watermark Remover — remove the Made with Gamma badge from PDF & PPTX](banner.webp)

一款 [Agent 技能](SKILL.md)，让 AI 编程助手能够移除从 [Gamma.app](https://gamma.app) 导出的 PDF 和 PowerPoint (.pptx) 文件中的 **"Made with Gamma"** 水印。安装后，只需对你的 Agent 说：

> *"帮我去掉 deck.pdf 里的 Gamma 水印"*（"remove the gamma watermark from deck.pdf"）

移除过程是**结构化且无损的** — 水印徽标及其 gamma.app 超链接作为文档对象被直接删除；不会重新渲染，文字保持可选中，幻灯片保持可编辑。整个处理完全在本地完成。

## 安装

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

也支持项目级安装：将文件放入任意仓库的 `.claude/skills/gamma-watermark-remover/` 目录下，或放入你的 OpenClaw 工作区 `skills/` 目录。只需一个 `SKILL.md` — 两种 Agent 的格式完全一致。

## 技能功能

1. 验证文件（`.pdf` / `.pptx`，仅限用户自有的导出文件）
2. 按需安装 CLI：[`pip install gamma-watermark-remover`](https://pypi.org/project/gamma-watermark-remover/)
3. 执行移除并解读结果（包括当水印已被扁平化为页面图像、无法通过结构化方式移除时诚实报告的 `may_remain` 标志）
4. 提醒用户检查清理后的文件并保留原始文件

## 相关资源

- **CLI + Python 库**：[gammaremover/gamma-watermark-remover](https://github.com/gammaremover/gamma-watermark-remover)（[PyPI](https://pypi.org/project/gamma-watermark-remover/)）
- **网页版（无需安装，浏览器内运行，无需上传）**：[gammaremover.com](https://gammaremover.com)
- 工作原理：[检测逻辑详解](https://github.com/gammaremover/gamma-watermark-remover#how-detection-works)

## 负责任使用

用于清除**你创建或有权修改的文件**中的导出品牌标识 — 如客户演示文稿、课堂作业、作品集。Gamma 官方的无水印方案是其[付费计划](https://gammaremover.com/en/blog/gamma-free-vs-pro-watermark/)，重度用户可能确实更适合选择付费版本。

## 许可证

MIT
