# Colab Mosaic Clip

[![Python](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![Colab](https://img.shields.io/badge/platform-Google%20Colab-orange.svg)](https://colab.research.google.com/github/hiroaki-com/colab-mosaic-clip/blob/main/mosaic_clip_en.ipynb)
[![FFmpeg](https://img.shields.io/badge/FFmpeg-compatible-blueviolet.svg)](https://ffmpeg.org/)

English | [日本語](./README.md)

https://github.com/user-attachments/assets/984e6d25-5342-4532-be71-c32714989bd3

### Overview

A Google Colab notebook that applies a mosaic or solid-color mask to any time range and region of a video and exports it as MP4. No installation required — free to use.

Supported input formats: `.mov` `.mp4` `.avi` `.mkv` `.webm`

#### Key Features

- Record start/end timestamps with a single button click on the video player
- Intuitively place mosaic regions by clicking directly on the frame image
- Two masking patterns: pixelated mosaic and solid color (any color)
- Apply to multiple regions at once, with support for add / move / resize / undo
- Preview the result in place before exporting
- Save to local download or Google Drive

#### Who It's For

- Developers who want to quickly remove personal information captured in screen recordings
- Engineers who need mosaic processing without writing ffmpeg commands
- Technical writers removing sensitive information from demo or tutorial videos
- Anyone who wants to post a video containing account info or API keys to social media

---

### Quick Start

#### Runtime

```
https://colab.research.google.com/github/hiroaki-com/colab-mosaic-clip/blob/main/mosaic_clip_en.ipynb
```

> Runs on a CPU runtime. No GPU required.

#### Basic Steps

1. Open the notebook in Google Colab
2. Run the Setup cell (first time only)
3. Upload your video file
4. Play the video and record the start and end timestamps for the mosaic
5. Click on the frame image to place mosaic regions
6. Set the output width and save destination, then run the export
7. Check the preview
8. Save to local storage or Google Drive

---

### Mosaic Controls

| Action | Behavior |
|---|---|
| Click while ➕ is ON | Add a new mosaic region (automatically turns OFF after adding) |
| Drag inside region | Move the mosaic region |
| Drag bottom-right □ | Resize the mosaic region |
| ↩ Undo | Remove the most recently added region |
| 🗑 Clear All | Reset all regions |
| 👁 Preview | Preview the masked result before exporting |

Adding multiple regions allows all of them to be processed in a single export.

---

### Mosaic Patterns

| Pattern | Description | Best For |
|---|---|---|
| Mosaic | Pixelates at the specified block size | Blurring faces, text, or any content |
| Solid | Fills with a chosen color | Completely hiding content (black bar, gray, etc.) |

#### Granularity (Mosaic only)

| Value | Appearance |
|:---:|---|
| Low (around 2–8) | Fine mosaic |
| High (around 20–40) | Coarse mosaic |

---

### Export Settings

| Option | Range | Notes |
|---|---|---|
| Output format | MP4 (H.264) | Audio is preserved if present in the source video |
| Output width | 240px – 1920px | Aspect ratio is maintained automatically |
| Mosaic range | Start sec – End sec | When start = end, only a single frame is processed |

---

### Save Options

| Destination | Description |
|---|---|
| Download locally | Save via the browser's download dialog |
| Save to Google Drive | Auto-copy to a specified path (includes mount) |
| Both | Run both of the above simultaneously |

---

### Tech Stack

- Runtime: Google Colab (Python 3.10+)
- Conversion engine: FFmpeg
- UI: ipywidgets
- Image processing: Pillow
- Storage: Google Drive API / local download

---

### License

MIT License. See [LICENSE](LICENSE) for details.

### Credits

- [FFmpeg](https://ffmpeg.org/) - Video conversion engine
- [Google Colab](https://colab.research.google.com/) - Free runtime environment
- [Pillow](https://python-pillow.org/) - Image processing library

### Support

- Bug reports: [Issues](https://github.com/hiroaki-com/colab-mosaic-clip/issues)
- Questions & discussion: [Discussions](https://github.com/hiroaki-com/colab-mosaic-clip/discussions)
