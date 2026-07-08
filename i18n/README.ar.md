# Gamma Watermark Remover — مهارة وكيل (Claude Code و OpenClaw )

[![Claude Code](https://img.shields.io/badge/Claude%20Code-skill-8b3dff)](https://docs.anthropic.com/en/docs/claude-code)
[![OpenClaw](https://img.shields.io/badge/OpenClaw-skill-ff6b35)](https://github.com/gammaremover/gamma-watermark-remover-skill)
[![CLI on PyPI](https://img.shields.io/pypi/v/gamma-watermark-remover?color=8b3dff&label=CLI%20on%20PyPI)](https://pypi.org/project/gamma-watermark-remover/)
[![License: MIT](https://img.shields.io/badge/License-MIT-8b3dff.svg)](../LICENSE)
[![Web version](https://img.shields.io/badge/Web%20version-gammaremover.com-8b3dff)](https://gammaremover.com)

[English](../README.md) | [简体中文](README.zh-CN.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [Español](README.es.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [Português](README.pt-BR.md) | [Русский](README.ru.md) | [Türkçe](README.tr.md) | [Italiano](README.it.md) | [Bahasa Indonesia](README.id.md) | **العربية** | [हिन्दी](README.hi.md)

![Gamma Watermark Remover — remove the Made with Gamma badge from PDF & PPTX](../banner.webp)

[مهارة وكيل](../SKILL.md) تتيح لوكلاء البرمجة بالذكاء الاصطناعي إزالة العلامة المائية **"Made with Gamma"** من ملفات PDF وPowerPoint (.pptx) المصدّرة من [Gamma.app](https://gamma.app). بعد التثبيت، ما عليك سوى أن تطلب من وكيلك:

> *"أزل علامة Gamma المائية من deck.pdf"* ("remove the gamma watermark from deck.pdf")

الإزالة **بنيوية وبدون فقدان بيانات** — يتم حذف شارة العلامة المائية ورابطها التشعبي إلى gamma.app كعناصر مستند؛ لا يُعاد أي تصيير، ويبقى النص قابلاً للتحديد والشرائح قابلة للتعديل. تتم المعالجة بالكامل محلياً.

## التثبيت

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

يمكن أيضاً التثبيت على مستوى المشروع: ضع الملف في `.claude/skills/gamma-watermark-remover/` داخل أي مستودع، أو في مجلد `skills/` في مساحة عمل OpenClaw الخاصة بك. ملف `SKILL.md` واحد — التنسيق متطابق لكلا الوكيلين.

## ما تفعله المهارة

1. تتحقق من الملف (`.pdf` / `.pptx`، ملفات التصدير الخاصة بالمستخدم فقط)
2. تثبّت أداة CLI عند الحاجة: [`pip install gamma-watermark-remover`](https://pypi.org/project/gamma-watermark-remover/)
3. تنفذ الإزالة وتفسر النتيجة (بما في ذلك علامة `may_remain` الصادقة عندما تكون الشارة مدمجة في صورة الصفحة ولا يمكن إزالتها بنيوياً)
4. تذكّر المستخدم بمراجعة الملف المنظّف والاحتفاظ بالملف الأصلي

## موارد ذات صلة

- **CLI + مكتبة Python**: [gammaremover/gamma-watermark-remover](https://github.com/gammaremover/gamma-watermark-remover) ([PyPI](https://pypi.org/project/gamma-watermark-remover/))
- **نسخة الويب (بدون تثبيت، تعمل في المتصفح، بدون رفع ملفات)**: [gammaremover.com](https://gammaremover.com)
- آلية العمل: [شرح منطق الكشف](https://github.com/gammaremover/gamma-watermark-remover#how-detection-works)

## الاستخدام المسؤول

لإزالة العلامة التجارية للتصدير من **الملفات التي أنشأتها أو لديك الحق في تعديلها** — عروض العملاء، واجبات دراسية، أعمال معرض الأعمال. الطريقة الرسمية من Gamma لإزالة العلامة المائية هي [الخطة المدفوعة](https://gammaremover.com/en/blog/gamma-free-vs-pro-watermark/)، التي قد يفضلها المستخدمون الكثيفون فعلاً.

## الرخصة

MIT
