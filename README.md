# I-Combinator

## Overview

I-Combinator started as a Python-based script for home use that evolved into a web application designed to combine images vertically or horizontally without cropping any pixels by extending the canvas to accommodate all input images. Inspired to build when imageLR services crashed and not recover in a timely manner.

Everything runs client-side in the browser — images never leave your device.

## Features

- **Stacks images vertically or horizontally**
- **Multi-file picker, drag & drop, and paste** (Ctrl/Cmd+V) — add any number of images at once
- **Thumbnail previews** with drag-to-reorder, move buttons, and per-image remove
- **Live preview** — the result re-stitches automatically as you change anything
- **Sizing modes** — match the smallest image (default), match the largest, or keep original sizes
- **Gap & background color** — optional spacing between images with a custom fill color
- **Export options** — JPEG, PNG, or WebP with a quality slider and date-stamped filenames
- **Dark mode** — follows your system theme
- Remembers your settings between visits (stored locally)

## Usage

Open `index.html` in any modern browser — no build step, no dependencies, no server required.

The original Python version lives in `combiner.ipynb`.
