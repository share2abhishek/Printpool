# Radixile PrintPool

**Batch document printing & conversion for Windows (and macOS).**
Add many files, pick a printer, and print or convert them all in one go — PDFs, Word/Excel/PowerPoint, OpenDocument, images, HTML, and more.

Published by **Radixile Technology Solutions LLP**, Pune, MH, India.

---

## 📖 Documentation

| Guide | For |
|-------|-----|
| **[Installation Guide](docs/INSTALLATION.md)** | Step-by-step download & install (Windows / macOS), upgrades, uninstall, troubleshooting. |
| **[User Guide / Help](docs/HELP.md)** | How to use every feature, in plain English. |
| **[Features](docs/FEATURES.md)** | Full feature list and the 35+ supported file formats. |
| **[Building from source](BUILD.md)** | For developers building their own installer. |
| **[Changelog](CHANGELOG.md)** · **[Release guide](RELEASE.md)** | Version history and how releases are published. |

---

## Download & install (Windows)

1. Download the latest installer from **[GitHub Releases](https://github.com/share2abhishek/printpool/releases/latest)** →
   `printpool-<version>-setup.exe` (open to everyone — no account or login needed).
2. Double-click it. It installs per-user (no admin needed).
3. First run is unsigned, so Windows SmartScreen may show **"Windows protected your PC"** →
   click **More info → Run anyway**. (See `SMARTSCREEN.txt` bundled with the app.)

The installer is **self-contained** — it bundles everything needed (LibreOffice for
Office/OpenDocument conversion, the OCR engine, and the print components), so it works
on a clean machine with no extra installs. Upgrades replace the previous version
automatically (a running copy is closed for you).

**System requirements:** Windows 10 or newer, ~1 GB free disk space.

---

## Using PrintPool

| Tab | What it does |
|-----|--------------|
| **Files** | Add documents (drag to reorder), then **Print All**. Per-file settings: copies, page range, duplex, orientation, paper size, print mode. |
| **Printers** | Click a printer to make it PrintPool's printer (saved). Defaults to the system default if you don't choose. |
| **Convert** | Convert files to another format and save them — no printing. PDF / Office / OpenDocument / images. Includes **PDF → Word/text** (extracts the text layer, or OCRs scanned PDFs). |
| **Preview** | Preview queued PDF documents before printing. |
| **History** | Every job printed. Select rows (or "select all") and **Reprint selected**, or reprint a single row. Export to CSV. |
| **Schedule** | Print the queue on a recurring schedule, or watch a folder and auto-print new files. |
| **Settings** | Default print mode, LibreOffice location (auto-detected), OCR language, minimise-to-tray. |

### Printing to PDF
Select **"Microsoft Print to PDF"** in the Printers tab, then **Print All** — PrintPool
asks for a **file name + location** (Save As) for each document and writes the PDF there.

### PDF → Word (OCR)
In **Convert**, choose a PDF and target **Word (DOCX)** / ODT / RTF / TXT. PDFs with a real
text layer convert instantly; scanned/image PDFs are OCR'd offline (language is set in
**Settings → OCR**: English, Hindi, Spanish, French).

---

## Building from source

Requires Node.js 18+ and (for Office/OCR features) an internet connection at build time.

```bash
npm install
npm run build:win:bundle     # Windows: self-contained installer → dist/
npm run build:mac:bundle     # macOS (must run on a Mac)
```

See **[BUILD.md](BUILD.md)** for lean vs. self-contained builds, OCR asset staging, and
the manual install checklist.

## Releasing / distribution

- **Versioning & changelog:** see **[CHANGELOG.md](CHANGELOG.md)** and **[RELEASE.md](RELEASE.md)**.
- **Publish to Bitbucket Downloads:** `npm run publish:bitbucket` (see RELEASE.md for credentials).

## Tech

Electron + React (electron-vite), packaged with electron-builder. Office/CAD conversion via
bundled LibreOffice; PDF text/OCR via pdf.js + Tesseract.js; printing via pdf-to-printer
(Windows) / `lp` (macOS/Linux).

## License & publisher

© 2026 Radixile Technology Solutions LLP, Pune, India. All rights reserved.
Bundles third-party components (LibreOffice — MPL/LGPL; SumatraPDF — GPLv3; Tesseract — Apache-2.0; pdf.js — Apache-2.0) under their respective licenses.
