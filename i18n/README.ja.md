# Gamma ウォーターマーク リムーバー — エージェントスキル for Claude Code and OpenClaw

[![Claude Code](https://img.shields.io/badge/Claude%20Code-skill-8b3dff)](https://docs.anthropic.com/en/docs/claude-code)
[![OpenClaw](https://img.shields.io/badge/OpenClaw-skill-ff6b35)](https://github.com/gammaremover/gamma-watermark-remover-skill)
[![CLI on PyPI](https://img.shields.io/pypi/v/gamma-watermark-remover?color=8b3dff&label=CLI%20on%20PyPI)](https://pypi.org/project/gamma-watermark-remover/)
[![License: MIT](https://img.shields.io/badge/License-MIT-8b3dff.svg)](../LICENSE)
[![Web version](https://img.shields.io/badge/Web%20version-gammaremover.com-8b3dff)](https://gammaremover.com)

[English](../README.md) | [简体中文](README.zh-CN.md) | **日本語** | [한국어](README.ko.md) | [Español](README.es.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [Português](README.pt-BR.md) | [Русский](README.ru.md) | [Türkçe](README.tr.md) | [Italiano](README.it.md) | [Bahasa Indonesia](README.id.md) | [العربية](README.ar.md) | [हिन्दी](README.hi.md)

![Gamma Watermark Remover — remove the Made with Gamma badge from PDF & PPTX](../banner.webp)

AI コーディングエージェントが [Gamma.app](https://gamma.app) からエクスポートした PDF および PowerPoint (.pptx) ファイルの **「Made with Gamma」** ウォーターマークを除去できるようにする[エージェントスキル](../SKILL.md)です。インストール後、エージェントに次のように頼むだけです：

> *「deck.pdf から Gamma のウォーターマークを削除して」*（"remove the gamma watermark from deck.pdf"）

除去は**構造的かつロスレス**です — ウォーターマークバッジとその gamma.app ハイパーリンクはドキュメントオブジェクトとして削除されます。再レンダリングは行われず、テキストは選択可能なまま、スライドは編集可能なまま維持されます。処理はすべてローカルで完結します。

## インストール

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

プロジェクトスコープでのインストールも可能です：任意のリポジトリ内の `.claude/skills/gamma-watermark-remover/` にファイルを配置するか、OpenClaw ワークスペースの `skills/` ディレクトリに配置してください。`SKILL.md` は1つだけ — 両エージェントで同一フォーマットです。

## スキルの機能

1. ファイルを検証（`.pdf` / `.pptx`、ユーザー自身のエクスポートファイルのみ対象）
2. CLI をオンデマンドでインストール：[`pip install gamma-watermark-remover`](https://pypi.org/project/gamma-watermark-remover/)
3. 除去を実行し結果を解釈（バッジがページ画像にフラット化されて構造的に除去できない場合の正直な `may_remain` フラグを含む）
4. クリーニング済みファイルの確認とオリジナルの保持をユーザーにリマインド

## 関連リソース

- **CLI + Python ライブラリ**：[gammaremover/gamma-watermark-remover](https://github.com/gammaremover/gamma-watermark-remover)（[PyPI](https://pypi.org/project/gamma-watermark-remover/)）
- **Web 版（インストール不要、ブラウザで動作、アップロード不要）**：[gammaremover.com](https://gammaremover.com)
- 仕組みの解説：[検出ロジックの説明](https://github.com/gammaremover/gamma-watermark-remover#how-detection-works)

## 責任ある使用

**自分が作成した、または修正する権利のあるファイル**のエクスポートブランディングを除去するためのものです — クライアント向け資料、授業の提出物、ポートフォリオ作品など。Gamma の公式のウォーターマークなしオプションは[有料プラン](https://gammaremover.com/en/blog/gamma-free-vs-pro-watermark/)であり、ヘビーユーザーには有料版の方が適している場合もあります。

## ライセンス

MIT
