# Gamma Watermark Remover — Skill Agen for Claude Code and OpenClaw

[![Claude Code](https://img.shields.io/badge/Claude%20Code-skill-8b3dff)](https://docs.anthropic.com/en/docs/claude-code)
[![OpenClaw](https://img.shields.io/badge/OpenClaw-skill-ff6b35)](https://github.com/gammaremover/gamma-watermark-remover-skill)
[![CLI on PyPI](https://img.shields.io/pypi/v/gamma-watermark-remover?color=8b3dff&label=CLI%20on%20PyPI)](https://pypi.org/project/gamma-watermark-remover/)
[![License: MIT](https://img.shields.io/badge/License-MIT-8b3dff.svg)](../LICENSE)
[![Web version](https://img.shields.io/badge/Web%20version-gammaremover.com-8b3dff)](https://gammaremover.com)

[English](../README.md) | [简体中文](README.zh-CN.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [Español](README.es.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [Português](README.pt-BR.md) | [Русский](README.ru.md) | [Türkçe](README.tr.md) | [Italiano](README.it.md) | **Bahasa Indonesia** | [العربية](README.ar.md) | [हिन्दी](README.hi.md)

![Gamma Watermark Remover — remove the Made with Gamma badge from PDF & PPTX](../banner.webp)

Sebuah [skill agen](../SKILL.md) yang memungkinkan agen pemrograman AI menghapus watermark **"Made with Gamma"** dari file PDF dan PowerPoint (.pptx) yang diekspor dari [Gamma.app](https://gamma.app). Setelah diinstal, cukup minta agen Anda:

> *"hapus watermark Gamma dari deck.pdf"* ("remove the gamma watermark from deck.pdf")

Penghapusan bersifat **struktural dan tanpa kehilangan data** — lencana watermark dan hyperlink gamma.app-nya dihapus sebagai objek dokumen; tidak ada yang di-render ulang, teks tetap bisa dipilih, slide tetap bisa diedit. Pemrosesan sepenuhnya dilakukan secara lokal.

## Instalasi

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

Instalasi tingkat proyek juga bisa dilakukan: letakkan file di `.claude/skills/gamma-watermark-remover/` di dalam repositori mana pun, atau di direktori `skills/` workspace OpenClaw Anda. Cukup satu `SKILL.md` — formatnya identik untuk kedua agen.

## Yang dilakukan skill ini

1. Memvalidasi file (`.pdf` / `.pptx`, hanya file ekspor milik pengguna)
2. Menginstal CLI sesuai kebutuhan: [`pip install gamma-watermark-remover`](https://pypi.org/project/gamma-watermark-remover/)
3. Menjalankan penghapusan dan menginterpretasi hasilnya (termasuk flag jujur `may_remain` ketika lencana telah diratakan ke dalam gambar halaman dan tidak bisa dihapus secara struktural)
4. Mengingatkan pengguna untuk memeriksa file yang sudah dibersihkan dan menyimpan file aslinya

## Sumber daya terkait

- **CLI + pustaka Python**: [gammaremover/gamma-watermark-remover](https://github.com/gammaremover/gamma-watermark-remover) ([PyPI](https://pypi.org/project/gamma-watermark-remover/))
- **Versi web (tanpa instalasi, berjalan di browser, tanpa unggah)**: [gammaremover.com](https://gammaremover.com)
- Cara kerjanya: [penjelasan logika deteksi](https://github.com/gammaremover/gamma-watermark-remover#how-detection-works)

## Penggunaan yang bertanggung jawab

Untuk membersihkan branding ekspor dari **file yang Anda buat atau berhak memodifikasi** — presentasi klien, tugas kuliah, karya portofolio. Cara resmi Gamma untuk menghilangkan watermark adalah [paket berbayar](https://gammaremover.com/en/blog/gamma-free-vs-pro-watermark/), yang mungkin benar-benar lebih cocok bagi pengguna berat.

## Lisensi

MIT
