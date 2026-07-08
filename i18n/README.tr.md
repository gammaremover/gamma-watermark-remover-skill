# Gamma Watermark Remover — Ajan Becerisi for Claude Code and OpenClaw

[![Claude Code](https://img.shields.io/badge/Claude%20Code-skill-8b3dff)](https://docs.anthropic.com/en/docs/claude-code)
[![OpenClaw](https://img.shields.io/badge/OpenClaw-skill-ff6b35)](https://github.com/gammaremover/gamma-watermark-remover-skill)
[![CLI on PyPI](https://img.shields.io/pypi/v/gamma-watermark-remover?color=8b3dff&label=CLI%20on%20PyPI)](https://pypi.org/project/gamma-watermark-remover/)
[![License: MIT](https://img.shields.io/badge/License-MIT-8b3dff.svg)](../LICENSE)
[![Web version](https://img.shields.io/badge/Web%20version-gammaremover.com-8b3dff)](https://gammaremover.com)

[English](../README.md) | [简体中文](README.zh-CN.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [Español](README.es.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [Português](README.pt-BR.md) | [Русский](README.ru.md) | **Türkçe** | [Italiano](README.it.md) | [Bahasa Indonesia](README.id.md) | [العربية](README.ar.md) | [हिन्दी](README.hi.md)

![Gamma Watermark Remover — remove the Made with Gamma badge from PDF & PPTX](../banner.webp)

[Gamma.app](https://gamma.app)'ten dışa aktarılan PDF ve PowerPoint (.pptx) dosyalarından **"Made with Gamma"** filigranını yapay zeka kodlama ajanlarının kaldırmasına olanak tanıyan bir [ajan becerisi](../SKILL.md). Kurulumdan sonra ajanınıza şunu söylemeniz yeterlidir:

> *"deck.pdf dosyasından Gamma filigranını kaldır"* ("remove the gamma watermark from deck.pdf")

Kaldırma işlemi **yapısal ve kayıpsızdır** — filigran rozeti ve gamma.app bağlantısı belge nesneleri olarak silinir; hiçbir şey yeniden render edilmez, metin seçilebilir kalır, slaytlar düzenlenebilir kalır. İşlem tamamen yerel olarak gerçekleştirilir.

## Kurulum

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

Proje kapsamlı kurulum da mümkündür: dosyayı herhangi bir deponun `.claude/skills/gamma-watermark-remover/` dizinine veya OpenClaw çalışma alanınızın `skills/` dizinine yerleştirin. Tek bir `SKILL.md` — format her iki ajan için de aynıdır.

## Becerinin yaptıkları

1. Dosyayı doğrular (`.pdf` / `.pptx`, yalnızca kullanıcının kendi dışa aktarımları)
2. CLI'yi ihtiyaç durumunda kurar: [`pip install gamma-watermark-remover`](https://pypi.org/project/gamma-watermark-remover/)
3. Kaldırma işlemini çalıştırır ve sonucu yorumlar (rozet sayfa görüntüsüne düzleştirilmiş ve yapısal olarak kaldırılamadığında dürüst `may_remain` bayrağı dahil)
4. Kullanıcıya temizlenmiş dosyayı incelemesini ve orijinali saklamasını hatırlatır

## İlgili kaynaklar

- **CLI + Python kütüphanesi**: [gammaremover/gamma-watermark-remover](https://github.com/gammaremover/gamma-watermark-remover) ([PyPI](https://pypi.org/project/gamma-watermark-remover/))
- **Web sürümü (kurulum gerektirmez, tarayıcınızda çalışır, yükleme gerekmez)**: [gammaremover.com](https://gammaremover.com)
- Nasıl çalışır: [algılama mantığı açıklaması](https://github.com/gammaremover/gamma-watermark-remover#how-detection-works)

## Sorumlu kullanım

**Oluşturduğunuz veya değiştirme hakkına sahip olduğunuz dosyalardaki** dışa aktarma markasını temizlemek içindir — müşteri sunumları, ders ödevleri, portfolyo çalışmaları. Gamma'nın filigrансız resmi yolu [ücretli planıdır](https://gammaremover.com/en/blog/gamma-free-vs-pro-watermark/) ve yoğun kullanıcılar bunu gerçekten tercih edebilir.

## Lisans

MIT
