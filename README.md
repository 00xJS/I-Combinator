# I-Combinator

**[Try it live →](https://i-combinator.netlify.app/)**

Combine images side by side or stacked, without cropping — entirely in your browser.

## Overview

I-Combinator started as a Python script for home use that evolved into a web application designed to combine images vertically or horizontally without cropping any pixels, extending the canvas to accommodate all input images. Inspired to build when imageLR went down and didn't recover in a timely manner.

Everything runs client-side. The app makes no network requests of any kind — no fetch, no XHR, no external scripts, styles, or fonts — so your images never leave your device.

## Features

- **Stacks images vertically or horizontally**
- **Multi-file picker, drag & drop, and paste** (Ctrl/Cmd+V) — add any number of images at once
- **Thumbnail previews** with drag-to-reorder, move buttons, and per-image remove
- **Live preview** — the result re-stitches automatically as you change anything
- **Sizing modes** — match the smallest image (default), match the largest, or keep original sizes
- **Gap & background color** — optional spacing between images with a custom fill color
- **Export options** — JPEG, PNG, or WebP with a quality slider and date-stamped filenames
- **Dark interface** — a single focused dark theme
- Remembers your settings between visits (stored locally)

## Implementation notes

One HTML file, no dependencies, no build step. A few details worth knowing:

- **Browsers fail silently on oversized canvases.** They cap per-side dimensions (~16k px) and, on iOS, total canvas *area* — past the limit `drawImage` quietly no-ops and the export comes back blank with no error thrown. I-Combinator draws, verifies a pixel actually landed, and retries at half scale until the canvas is real.
- Export goes through `canvas.toBlob()` rather than data URLs, so large stitches don't hold the entire image in memory twice.
- Status changes are announced through ARIA live regions, every control is keyboard-operable, and text meets WCAG AA contrast.

## Usage

Open `index.html` in any modern browser — no build step, no dependencies, no server required.

The original Python version lives in `combiner.ipynb`.

---

Part of the [Observation Deck](https://observation-deck.netlify.app/).
