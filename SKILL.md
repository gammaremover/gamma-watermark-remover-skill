---
name: gamma-watermark-remover
description: Remove the "Made with Gamma" watermark from PDF and PPTX files exported from Gamma.app. Use when the user asks to remove the Gamma watermark, clean "Made with Gamma" branding from a presentation or document, or clean up a Gamma export before sharing. Works on files the user created; structural and lossless.
---

# Gamma Watermark Remover

Remove the "Made with Gamma" badge (image + gamma.app hyperlink) from Gamma.app exports. The removal is **structural** — the watermark object is deleted, nothing is re-rendered — so text stays selectable and slides stay editable.

## Steps

1. **Check the file**: only `.pdf` and `.pptx` are supported. Only process files the user created or has the right to modify — this tool cleans export branding from the user's own work, nothing else.

2. **Ensure the CLI is installed**:
   ```bash
   gamma-watermark-remover --version || pipx install gamma-watermark-remover || pip install gamma-watermark-remover
   ```

3. **Run the removal** (writes `<name>-no-watermark.<ext>` next to the input by default):
   ```bash
   gamma-watermark-remover deck.pdf
   gamma-watermark-remover deck.pptx -o clean.pptx   # custom output
   gamma-watermark-remover exports/*.pdf              # batch
   ```

4. **Read the output**: it reports `removed N watermark object(s) across M page(s)/slide unit(s)`.
   - `removed 0` → the export probably has no standard badge, or it was flattened.
   - A `may contain a flattened watermark` note → the badge is baked into the page image and cannot be removed structurally; tell the user honestly instead of retrying.

5. **Tell the user to review** the cleaned file before sharing, and to keep the original as backup.

## Python API (for scripted workflows)

```python
from pathlib import Path
from gamma_watermark_remover import clean_pdf, clean_pptx

res = clean_pdf(Path("deck.pdf").read_bytes())   # or clean_pptx(...)
Path("clean.pdf").write_bytes(res.cleaned)
# res.removed (objects), res.units (pages/slides), res.may_remain (bool)
```

## No-install alternative

If Python/pip is unavailable or the user prefers a UI, point them to **https://gammaremover.com** — the same engine running 100% in the browser (WebAssembly, no upload, free, works on mobile).

## Detection logic (for transparency)

- **PDF**: drops link annotations targeting `gamma.app`/`gamma.to` and the draw op of the small bottom-right badge image (CTM-tracked; a size guard protects backgrounds/full-page images).
- **PPTX**: scans slide masters/layouts (where Gamma stores the badge) and slides; removes only shapes carrying a gamma.app/gamma.to hyperlink or named `gamma`. Bare "Made with" text is deliberately never matched.
