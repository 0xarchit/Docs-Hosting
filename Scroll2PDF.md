---
label: Scroll2PDF
icon: file
description: "Auto-Scrolling Webpage Capture to PDF with PyQt6"
order: 97
tags: [Python, PyQt6, Screenshot, PDF]
---

# :icon-file: Auto-Scrolling Webpage Capture to PDF

![Python](https://img.shields.io/badge/Python-3.13-blue) ![PyQt6](https://img.shields.io/badge/PyQt6-blue) ![PDF](https://img.shields.io/badge/PDF-export-red)

:icon-mark-github: **GitHub**: [0xarchit/Scroll-To-Pdf](https://github.com/0xarchit/Scroll-To-Pdf)

A desktop application built with PyQt6 that automatically scrolls through a webpage, captures screenshots, stitches them, and exports the result as a multi-page PDF.

## :icon-device-desktop: Screenshots

+++ Software Interface
![Software Interface](Public/Scroll2PDF/software.png)
+++

## :icon-device-desktop: Overview

When you need a PDF of an entire webpage (including content below the fold), manual scrolling and screenshotting is tedious. **AutoScrollCapturePDF** automates:

1. Scrolling through the page
2. Taking successive screenshots
3. Detecting end of page via image similarity
4. Concatenating and saving as PDF

Ideal for long articles, reports, dashboards, and documentation pages.

---

## :icon-rocket: Features

- Configurable scroll delay, height, and max scroll count
- Automatic end-of-page detection (image similarity threshold)
- Preview stitched result before export
- Primary and fallback PDF export methods (Pillow and img2pdf)
- Dark-themed, responsive PyQt6 GUI
- Cross-platform (Windows/macOS/Linux)

---

## :icon-terminal: Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/0xarchit/Scroll-To-Pdf.git
   cd ScreenShotToPdf
   ```

2. (Optional) Create a virtual environment:
   ```bash
   python -m venv .venv
   .venv\Scripts\activate   # Windows
   source .venv/bin/activate  # macOS/Linux
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Ensure `app_icon.ico` sits alongside `main.py` in the project root.

---

## :icon-play: Usage

### Launching the Application

```bash
python main.py
```

The main window appears. Adjust settings then click **Start Capture**.

### Settings Panel

| Setting                   | Description                                               |
|---------------------------|-----------------------------------------------------------|
| Delay between scrolls     | Seconds to wait after each scroll (0.1 - 5.0)             |
| Max scrolls (0 = unlimited) | Maximum number of scroll actions before stopping     |
| Scroll height (0 = auto)  | Vertical pixels per scroll (0 uses default heights)       |
| Fullscreen mode (F11)     | Toggle auto height for full-screen vs windowed browsing  |

### Capture Workflow

1. Click **Start Capture** → 3‑second countdown → window minimizes
2. Focus browser and let it scroll+capture automatically
3. Status bar displays live updates and screenshot count
4. Capture stops on page end or reaching max scrolls
5. Window restores with **Preview**, **Save**, and **Clear** options

### Previewing

Click **Preview Screenshots** to open a stitched image of all screenshots. Close preview to return.

### Exporting to PDF

1. Click **Save as PDF**
2. Choose destination file path (`.pdf`)
3. Application attempts Pillow export; on failure, uses `img2pdf` fallback


---

## :icon-package: Architecture

- **`main.py`**: GUI, settings, thread orchestration
- **`CaptureThread`**: Runs scrolling & screenshot logic on background thread
- **Image Similarity**: Grayscale thumbnails compared to detect end of page
- **PDF Export**: Multi-page via Pillow or `img2pdf` fallback

---

## :icon-Workflow: How It Works

1. **Initial Delay**: 3 seconds to switch focus to browser
2. **Scroll Loop**:
   - Grab full-screen screenshot
   - Compare with previous (100×100 grayscale threshold)
   - If similar beyond 95%, capture final part and exit
   - Else, scroll down by configured height and repeat
3. **Signal UI**: `screenshot_taken`, `status_update`, `capture_complete` signals update progress

---

## :icon-sliders: Configuration Parameters

| Parameter     | Default | Unit       | Description                                 |
|---------------|---------|------------|---------------------------------------------|
| `delay`       | 0.5     | seconds    | Wait time between scroll & capture          |
| `max_scrolls` | 10      | counts     | Zero = infinite until end-of-page detected  |
| `manual_height` | 0     | pixels     | Override auto scroll height if > 0          |
| `is_fullscreen`| False  | boolean    | Use fullscreen height (1300px) vs windowed (1245px) |

---

## :icon-download: Packaging as Executable

This project includes a PyInstaller spec (`main.spec`):

```bash
pip install pyinstaller
pyinstaller main.spec
```

Look under `dist/` or `build/` for the generated executable.

---

## :icon-tools: Troubleshooting

- **Blank screenshots**: Ensure browser window is not minimized and is in focus.
- **OCR or hidden UI elements**: Use headless capture libraries or adjust scroll offsets.
- **Permission errors**: On macOS, grant screen recording privileges.
- **PDF Export fails**: Install `img2pdf` via `pip install img2pdf`.

---

## :icon-question: FAQ

Q: Can I capture only part of a page?

A: Not currently; feature coming soon (scroll region selection).

Q: Why are some screenshots repeated?

A: Overlapping scroll height may cause repeats. Increase `delay` or adjust `scroll height`.

Q: How do I change similarity threshold?

A: Hardcoded to 0.95; modify `images_are_similar()` in `CaptureThread`.

---

## :icon-git-branch: Contributing

1. Fork the repo
2. Create a feature branch (`git checkout -b feature/YourFeature`)
3. Commit your changes (`git commit -m 'Add feature'`)
4. Push to your branch (`git push origin feature/YourFeature`)
5. Open a Pull Request

Please follow [PEP8](https://www.python.org/dev/peps/pep-0008/) and include tests for new functionality.

---

## :icon-law: License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
