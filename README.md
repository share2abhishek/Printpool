# Radixile PrintPool — Batch Document Printing & Conversion for Windows

> **Print or convert many files at once.** Add a whole folder of PDFs, Word, Excel,
> PowerPoint, images, HTML and 35+ file types, pick a printer, and print or convert them
> all in one click — a fast, free, modern **batch printing** app for Windows and macOS.

<p align="center">
  <a href="https://github.com/share2abhishek/Printpool/releases/latest"><img alt="Download" src="https://img.shields.io/github/v/release/share2abhishek/Printpool?label=download&style=for-the-badge"></a>
  <a href="https://github.com/share2abhishek/Printpool/releases"><img alt="Total downloads" src="https://img.shields.io/github/downloads/share2abhishek/Printpool/total?style=for-the-badge"></a>
  <img alt="Platform" src="https://img.shields.io/badge/platform-Windows%20%7C%20macOS-blue?style=for-the-badge">
  <img alt="License" src="https://img.shields.io/badge/license-Proprietary-lightgrey?style=for-the-badge">
</p>

**Radixile PrintPool** is a desktop **batch document printing and conversion** tool — a modern
alternative to tools like Print Conductor and Print Wizard. Instead of opening Word, Excel,
your PDF reader and an image viewer one by one, you build a single print queue and PrintPool
prints (or converts) everything for you, with per-document copies, page ranges, and
double-sided settings.

Published by **Radixile Technology Solutions LLP**, Pune, MH, India.

**Keywords:** batch printing software · print multiple files at once · bulk print PDF / Word /
Excel / PowerPoint · print all files in a folder · batch document converter · PDF to Word (OCR)
· print queue · Windows printing app.

### Who it's for

- 🏢 **Offices** printing daily reports, invoices, or statements in bulk.
- 🖨️ **Print shops & admins** running large mixed-format print jobs unattended.
- 📚 **Anyone** who regularly prints the same set of documents (drag, save the list, reprint).
- 🔄 People who need to **convert** batches of files (PDF ⇄ Office ⇄ images, PDF → Word via OCR).

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

## Frequently asked questions

**How do I print multiple files at once on Windows?**
Install PrintPool, drag your files (PDF, Word, Excel, PowerPoint, images, and more) onto the
window, pick a printer, and click **Print All**. PrintPool prints every document in order,
applying each file's copies / page range / duplex settings. See the [User Guide](docs/HELP.md).

**Can it print a whole folder automatically?**
Yes. Set a **Watch Folder** in Settings and any new file dropped there is printed automatically.
You can also **schedule** the queue to print once, daily, or weekly.

**Is PrintPool a free alternative to Print Conductor?**
PrintPool is a modern batch-printing app covering the same core job — printing many mixed-format
documents in one run — with conversion, OCR, scheduling, and reprint from history built in.

**What file types can it print?**
PDF, Word (`doc`/`docx`), Excel (`xls`/`xlsx`), PowerPoint (`ppt`/`pptx`), OpenDocument, images
(JPG, PNG, TIFF, WebP…), HTML, email (`eml`/`msg`), CAD (`dwg`/`dxf`), and more — **35+ formats**.
See [FEATURES.md](docs/FEATURES.md#supported-file-formats).

**Can it convert PDF to Word?**
Yes — the **Convert** tab extracts a PDF's text layer, or OCRs scanned PDFs offline
(English, Hindi, Spanish, French) to DOCX/ODT/RTF/TXT.

**Does it need admin rights or LibreOffice installed?**
No. The Windows installer is per-user (no admin) and self-contained — it bundles LibreOffice and
the OCR engine, so it works on a clean machine offline.

---

## License & publisher

© 2026 Radixile Technology Solutions LLP, Pune, India. All rights reserved.
Bundles third-party components (LibreOffice — MPL/LGPL; SumatraPDF — GPLv3; Tesseract — Apache-2.0; pdf.js — Apache-2.0) under their respective licenses.
