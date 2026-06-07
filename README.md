# Radixile PrintPool — Batch Printing, Conversion & Print Shop Billing for Windows

> **Print, convert, and bill — all in one app.** Add a whole folder of PDFs, Word, Excel,
> PowerPoint, images, HTML and 35+ file types, pick a printer, print or convert them all in one
> click, and generate professional numbered receipts for your clients.
> A fast, free, modern **batch printing + billing** app for Windows and macOS.

<p align="center">
  <a href="https://github.com/share2abhishek/Printpool/releases/latest"><img alt="Download" src="https://img.shields.io/github/v/release/share2abhishek/Printpool?label=download&style=for-the-badge"></a>
  <a href="https://github.com/share2abhishek/Printpool/releases"><img alt="Total downloads" src="https://img.shields.io/github/downloads/share2abhishek/Printpool/total?style=for-the-badge"></a>
  <img alt="Platform" src="https://img.shields.io/badge/platform-Windows%20%7C%20macOS-blue?style=for-the-badge">
  <img alt="License" src="https://img.shields.io/badge/license-Proprietary-lightgrey?style=for-the-badge">
</p>

**Radixile PrintPool** is a desktop **batch document printing, conversion, and billing** tool —
a modern alternative to tools like Print Conductor and Print Wizard. Instead of opening Word,
Excel, your PDF reader and an image viewer one by one, you build a single print queue and PrintPool
prints (or converts) everything for you, with per-document copies, page ranges, and double-sided
settings.

In addition, PrintPool includes a **complete print shop billing module**: generate numbered
receipts for walk-in clients, track customers, apply discounts and tax, accept multiple payment
modes, and view daily revenue reports — all built in, with no subscription or extra software.

Published by **Radixile Technology Solutions LLP**, Pune, MH, India.

**Keywords:** batch printing software · print multiple files at once · bulk print PDF / Word /
Excel / PowerPoint · print all files in a folder · batch document converter · PDF to Word (OCR)
· print queue · Windows printing app · print shop billing software · receipt generator
· client billing app · print shop management software.

### Who it's for

- 🖨️ **Print shops & copy centres** — bill clients, track payments, manage walk-in customers, and run reports.
- 🏢 **Offices** printing daily reports, invoices, or statements in bulk.
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

1. Download the latest installer from **[GitHub Releases](https://github.com/share2abhishek/Printpool/releases/latest)** →
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

### Printing & Conversion

| Tab | What it does |
|-----|--------------|
| **Files** | Add documents (drag to reorder), then **Print All**. Per-file settings: copies, page range, duplex, orientation, paper size, print mode. |
| **Printers** | Click a printer to make it PrintPool's printer (saved). Defaults to the system default if you don't choose. |
| **Convert** | Convert files to another format and save them — no printing. PDF / Office / OpenDocument / images. Includes **PDF → Word/text** (extracts text layer, or OCRs scanned PDFs). |
| **Preview** | Preview queued PDF documents before printing. |
| **History** | Every job printed. Select rows and **Reprint selected**, or reprint a single row. Export to CSV. |
| **Schedule** | Print the queue on a recurring schedule, or watch a folder and auto-print new files. |
| **Settings** | Default print mode, LibreOffice location, OCR language, billing rates, shop details, minimise-to-tray. |

### 🆕 Print Shop Billing *(new in v1.0)*

| Tab | What it does |
|-----|--------------|
| **🧾 Billing** | Select printed jobs as line items, add extra services (lamination, binding, scanning…), apply a flat or % discount, set tax, pick a payment mode (Cash / UPI / Card / Credit), and click **Generate Bill** to get a numbered receipt. View and reprint any past receipt. |
| **👥 Clients** | Save walk-in customers with name, phone, email, and notes. See each client's total spend, bill count, and last visit. Click a client to view their full bill history. |
| **📊 Reports** | Daily / weekly / custom-range dashboard — revenue, pages printed, outstanding credit, top service, and payment breakdown. Sortable bills table with CSV export. |

### Receipt example

```
┌─────────────────────────────────────────────────────────┐
│  🖨️ My Print Shop                           Bill #0012   │
│  123 Main Road · +91 99999 99999 · GST: 29XXXXX         │
│  Date: 07 Jun 2026                                       │
├──────────────────────┬──────┬──────────┬────────────────┤
│  Item / Activity     │ Qty  │ Rate     │ Amount         │
├──────────────────────┼──────┼──────────┼────────────────┤
│  report.pdf          │ 12p  │ ₹2.00    │ ₹24.00         │
│  resume.docx         │  3p  │ ₹2.00    │  ₹6.00         │
│  Lamination (A4)     │  1×  │ ₹15.00   │ ₹15.00         │
├──────────────────────┴──────┴──────────┼────────────────┤
│                            Subtotal    │ ₹45.00         │
│                         Discount 10%  │  -₹4.50        │
│                            Tax 5%     │  +₹2.03        │
│                            TOTAL      │ ₹42.53         │
├────────────────────────────────────────┴────────────────┤
│  📱 UPI ✅   Page 1 of 1 · Thank you for visiting!       │
└─────────────────────────────────────────────────────────┘
```

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
- **Publish to GitHub Releases:** `npm run publish:github` (needs `GH_TOKEN` env var).
- **Publish to Bitbucket Downloads:** `npm run publish:bitbucket` (see RELEASE.md for credentials).

## Tech

Electron + React (electron-vite), packaged with electron-builder. Office/CAD conversion via
bundled LibreOffice; PDF text/OCR via pdf.js + Tesseract.js; printing via pdf-to-printer
(Windows) / `lp` (macOS/Linux). Billing data stored in plain JSON (zero extra dependencies).

---

## Frequently asked questions

**How do I print multiple files at once on Windows?**
Install PrintPool, drag your files (PDF, Word, Excel, PowerPoint, images, and more) onto the
window, pick a printer, and click **Print All**. PrintPool prints every document in order,
applying each file's copies / page range / duplex settings. See the [User Guide](docs/HELP.md).

**Can it print a whole folder automatically?**
Yes. Set a **Watch Folder** in Settings and any new file dropped there is printed automatically.
You can also **schedule** the queue to print once, daily, or weekly.

**Is PrintPool free to use?**
Yes — PrintPool is free to download and use. It covers the same core job as Print Conductor
(batch printing many mixed-format documents in one run), plus adds conversion, OCR, scheduling,
reprinting from history, and a full print-shop billing module.

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

**Can I use it for billing in a print shop?**
Yes. The built-in **Billing panel** lets you select printed jobs, add extra services
(lamination, binding, scanning…), apply discounts and tax, and generate a printable numbered
receipt. The **Clients panel** keeps a customer book, and the **Reports panel** shows daily
revenue and outstanding credit — no third-party billing software needed.

**What payment modes are supported?**
Cash, UPI, Card, and Credit (pay-later). Credit bills are flagged separately and can be settled
from the Billing or Reports panel at any time.

---

## License & publisher

© 2026 Radixile Technology Solutions LLP, Pune, India. All rights reserved.
Bundles third-party components (LibreOffice — MPL/LGPL; SumatraPDF — GPLv3; Tesseract — Apache-2.0; pdf.js — Apache-2.0) under their respective licenses.
