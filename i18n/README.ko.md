# Gamma 워터마크 제거기 — 에이전트 스킬 for Claude Code and OpenClaw

[![Claude Code](https://img.shields.io/badge/Claude%20Code-skill-8b3dff)](https://docs.anthropic.com/en/docs/claude-code)
[![OpenClaw](https://img.shields.io/badge/OpenClaw-skill-ff6b35)](https://github.com/gammaremover/gamma-watermark-remover-skill)
[![CLI on PyPI](https://img.shields.io/pypi/v/gamma-watermark-remover?color=8b3dff&label=CLI%20on%20PyPI)](https://pypi.org/project/gamma-watermark-remover/)
[![License: MIT](https://img.shields.io/badge/License-MIT-8b3dff.svg)](../LICENSE)
[![Web version](https://img.shields.io/badge/Web%20version-gammaremover.com-8b3dff)](https://gammaremover.com)

[English](../README.md) | [简体中文](README.zh-CN.md) | [日本語](README.ja.md) | **한국어** | [Español](README.es.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [Português](README.pt-BR.md) | [Русский](README.ru.md) | [Türkçe](README.tr.md) | [Italiano](README.it.md) | [Bahasa Indonesia](README.id.md) | [العربية](README.ar.md) | [हिन्दी](README.hi.md)

![Gamma Watermark Remover — remove the Made with Gamma badge from PDF & PPTX](../banner.webp)

[Gamma.app](https://gamma.app)에서 내보낸 PDF 및 PowerPoint (.pptx) 파일의 **"Made with Gamma"** 워터마크를 AI 코딩 에이전트가 제거할 수 있게 해주는 [에이전트 스킬](../SKILL.md)입니다. 설치 후 에이전트에게 다음과 같이 요청하기만 하면 됩니다:

> *"deck.pdf에서 Gamma 워터마크 제거해 줘"* ("remove the gamma watermark from deck.pdf")

제거는 **구조적이며 무손실**입니다 — 워터마크 배지와 gamma.app 하이퍼링크가 문서 객체로서 삭제됩니다. 재렌더링 없이 텍스트는 선택 가능하고 슬라이드는 편집 가능한 상태를 유지합니다. 모든 처리는 로컬에서 이루어집니다.

## 설치

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

프로젝트 범위 설치도 가능합니다: 아무 저장소의 `.claude/skills/gamma-watermark-remover/` 디렉토리에 파일을 넣거나, OpenClaw 워크스페이스의 `skills/` 디렉토리에 넣으세요. `SKILL.md` 하나만 있으면 됩니다 — 두 에이전트 모두 동일한 형식을 사용합니다.

## 스킬 기능

1. 파일 검증 (`.pdf` / `.pptx`, 사용자 소유의 내보내기 파일만 대상)
2. CLI를 필요 시 자동 설치: [`pip install gamma-watermark-remover`](https://pypi.org/project/gamma-watermark-remover/)
3. 제거를 실행하고 결과를 해석 (배지가 페이지 이미지에 병합되어 구조적으로 제거할 수 없는 경우의 정직한 `may_remain` 플래그 포함)
4. 사용자에게 정리된 파일 검토와 원본 보관을 안내

## 관련 자료

- **CLI + Python 라이브러리**: [gammaremover/gamma-watermark-remover](https://github.com/gammaremover/gamma-watermark-remover) ([PyPI](https://pypi.org/project/gamma-watermark-remover/))
- **웹 버전 (설치 불필요, 브라우저에서 실행, 업로드 불필요)**: [gammaremover.com](https://gammaremover.com)
- 작동 원리: [탐지 로직 설명](https://github.com/gammaremover/gamma-watermark-remover#how-detection-works)

## 책임 있는 사용

**본인이 만들었거나 수정 권한이 있는 파일**의 내보내기 브랜딩을 제거하기 위한 것입니다 — 클라이언트 프레젠테이션, 수업 과제, 포트폴리오 등. Gamma의 공식 워터마크 제거 방법은 [유료 플랜](https://gammaremover.com/en/blog/gamma-free-vs-pro-watermark/)이며, 자주 사용하는 분들은 유료 버전을 선호할 수 있습니다.

## 라이선스

MIT
