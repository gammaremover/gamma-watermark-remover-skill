# Gamma Watermark Remover — एजेंट स्किल for Claude Code and OpenClaw

[![Claude Code](https://img.shields.io/badge/Claude%20Code-skill-8b3dff)](https://docs.anthropic.com/en/docs/claude-code)
[![OpenClaw](https://img.shields.io/badge/OpenClaw-skill-ff6b35)](https://github.com/gammaremover/gamma-watermark-remover-skill)
[![CLI on PyPI](https://img.shields.io/pypi/v/gamma-watermark-remover?color=8b3dff&label=CLI%20on%20PyPI)](https://pypi.org/project/gamma-watermark-remover/)
[![License: MIT](https://img.shields.io/badge/License-MIT-8b3dff.svg)](../LICENSE)
[![Web version](https://img.shields.io/badge/Web%20version-gammaremover.com-8b3dff)](https://gammaremover.com)

[English](../README.md) | [简体中文](README.zh-CN.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [Español](README.es.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [Português](README.pt-BR.md) | [Русский](README.ru.md) | [Türkçe](README.tr.md) | [Italiano](README.it.md) | [Bahasa Indonesia](README.id.md) | [العربية](README.ar.md) | **हिन्दी**

![Gamma Watermark Remover — remove the Made with Gamma badge from PDF & PPTX](../banner.webp)

एक [एजेंट स्किल](../SKILL.md) जो AI कोडिंग एजेंट्स को [Gamma.app](https://gamma.app) से निर्यात की गई PDF और PowerPoint (.pptx) फ़ाइलों से **"Made with Gamma"** वॉटरमार्क हटाने की सुविधा देता है। इंस्टॉल करने के बाद, बस अपने एजेंट से कहें:

> *"deck.pdf से Gamma का वॉटरमार्क हटा दो"* ("remove the gamma watermark from deck.pdf")

हटाने की प्रक्रिया **संरचनात्मक और लॉसलेस** है — वॉटरमार्क बैज और उसके gamma.app हाइपरलिंक को डॉक्यूमेंट ऑब्जेक्ट के रूप में हटा दिया जाता है; कुछ भी दोबारा रेंडर नहीं होता, टेक्स्ट सेलेक्ट करने योग्य रहता है, स्लाइड्स संपादन योग्य रहती हैं। प्रोसेसिंग पूरी तरह लोकल होती है।

## इंस्टॉलेशन

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

प्रोजेक्ट-स्तरीय इंस्टॉलेशन भी काम करता है: फ़ाइल को किसी भी रिपॉजिटरी के `.claude/skills/gamma-watermark-remover/` में रखें, या अपने OpenClaw वर्कस्पेस की `skills/` डायरेक्टरी में। बस एक `SKILL.md` — दोनों एजेंट्स के लिए फ़ॉर्मेट बिल्कुल एक जैसा है।

## स्किल क्या करता है

1. फ़ाइल को वैलिडेट करता है (`.pdf` / `.pptx`, केवल उपयोगकर्ता की अपनी निर्यात फ़ाइलें)
2. आवश्यकतानुसार CLI इंस्टॉल करता है: [`pip install gamma-watermark-remover`](https://pypi.org/project/gamma-watermark-remover/)
3. हटाने की प्रक्रिया चलाता है और परिणाम की व्याख्या करता है (जिसमें ईमानदार `may_remain` फ़्लैग शामिल है जब बैज पेज इमेज में फ़्लैटन हो चुका हो और संरचनात्मक रूप से हटाया न जा सके)
4. उपयोगकर्ता को साफ़ की गई फ़ाइल की जाँच करने और मूल फ़ाइल रखने की याद दिलाता है

## संबंधित संसाधन

- **CLI + Python लाइब्रेरी**: [gammaremover/gamma-watermark-remover](https://github.com/gammaremover/gamma-watermark-remover) ([PyPI](https://pypi.org/project/gamma-watermark-remover/))
- **वेब संस्करण (इंस्टॉलेशन नहीं, ब्राउज़र में चलता है, अपलोड नहीं)**: [gammaremover.com](https://gammaremover.com)
- कैसे काम करता है: [डिटेक्शन लॉजिक की व्याख्या](https://github.com/gammaremover/gamma-watermark-remover#how-detection-works)

## ज़िम्मेदार उपयोग

**आपके द्वारा बनाई गई या जिन्हें संशोधित करने का अधिकार है उन फ़ाइलों** से निर्यात ब्रांडिंग हटाने के लिए — क्लाइंट प्रेज़ेंटेशन, क्लास सबमिशन, पोर्टफ़ोलियो पीस। Gamma का आधिकारिक वॉटरमार्क-मुक्त विकल्प उनका [पेड प्लान](https://gammaremover.com/en/blog/gamma-free-vs-pro-watermark/) है, जो भारी उपयोगकर्ताओं के लिए वास्तव में बेहतर हो सकता है।

## लाइसेंस

MIT
