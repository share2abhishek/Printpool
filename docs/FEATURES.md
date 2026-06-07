# Features — Radixile PrintPool

PrintPool is a cross-platform **batch document printing, conversion, and billing** desktop app:
add many files, pick a printer, print or convert them all in one go — and generate professional
receipts for your clients.

> See also: **[Installation Guide](INSTALLATION.md)** · **[User Guide](HELP.md)**

---

## At a glance

- 🖨️ **Batch printing** — queue many documents and print them all to one printer, in the order you choose.
- 📄 **Per-document settings** — copies, page range (e.g. `1-3,5`), single/double-sided (duplex), orientation, and paper size, set independently for each file.
- 🔀 **Smart print modes** — *Automatic* (default), *Direct* (use the file's own program), or *Via PDF* (convert first for precise control).
- 🧾 **Print to PDF** — print to "Microsoft Print to PDF" / XPS and choose where each PDF is saved.
- 🔄 **Document conversion** — convert between PDF, Office, OpenDocument, and image formats without printing. Only valid targets are offered for the files you pick.
- 🔍 **PDF → Word / text (OCR)** — extract a PDF's text layer instantly, or OCR scanned pages **offline** (English, Hindi, Spanish, French).
- 👁️ **Preview** — view queued PDFs before printing.
- ⏰ **Schedule** — print the queue once, daily, or weekly at a set time.
- 📂 **Watch folder** — auto-print any new file dropped into a chosen folder.
- 💾 **Saved lists** — save a document set (with all its settings) and reload it later.
- 📋 **History + reprint** — full log of every job with status; reprint single or multiple rows; export to CSV.

### 🆕 Print Shop Billing Module *(new in v1.0)*
- 🧾 **Billing panel** — select printed jobs as billable line items, add extra services (lamination, binding, scanning…), apply flat or percentage discount, choose payment mode, and generate a numbered receipt.
- 🖨️ **Printable receipts** — auto-numbered bills (e.g. #0001) with shop name, GST, client info, itemised table, tax and discount rows. Print directly or save as PDF.
- 👥 **Client book** — save repeat customers with name, phone, email, and notes; view per-client spend history and bill records.
- 📊 **Reports dashboard** — daily / weekly / custom-range revenue summary, outstanding credit tracker, top service, payment breakdown, and sortable bills table with CSV export.
- ⚙️ **Configurable pricing** — set cost per page for A4/A3 × B&W/Colour; tax rate; currency (₹ $ € £ ¥); shop details and receipt footer.
- 🛍️ **Services catalog** — define extra services with name, price, and unit; seeded with common print-shop add-ons (Lamination, Spiral Binding, Scanning, Photo Print, Photocopy).
- ⏳ **Credit tracking** — mark bills as "Pay Later" and settle them later from the Billing or Reports panel.

---

## The tabs

| Tab | What it does |
|-----|--------------|
| **Files** | Add documents (drag to reorder), set per-file options, then **Print All**. |
| **Convert** | Convert files to another format and save them — no printing. Includes PDF → Word/text. |
| **Printers** | Click a printer to make it PrintPool's printer (saved). Falls back to the system default. |
| **Schedule** | Print the queue once / daily / weekly, or watch a folder and auto-print new files. |
| **History** | Every job printed, with status. Reprint (single or multi-select) and export to CSV. |
| **Preview** | Preview queued PDF documents before printing. |
| **🧾 Billing** *(new)* | Generate client bills from print activity, add extra services, apply discounts, view past receipts. |
| **👥 Clients** *(new)* | Customer book with spend history, bill records, and contact details. |
| **📊 Reports** *(new)* | Daily/range revenue dashboard, payment breakdown, outstanding credit, CSV export. |
| **Settings** | Default print mode, LibreOffice location, OCR language, watch folder, billing rates, shop details. |
| **Help** | Plain-English in-app guide (mirrored in [HELP.md](HELP.md)). |

---

## Supported file formats

PrintPool handles **35+ file types** out of the box.

| Category | Formats |
|----------|---------|
| **PDF** | `pdf` |
| **Images** | `jpg`, `jpeg`, `png`, `gif`, `bmp`, `tiff`, `tif`, `webp`, `ico` |
| **Vector** | `svg`, `wmf`, `emf` |
| **Word / Office (modern)** | `docx`, `xlsx`, `pptx` |
| **Word / Office (legacy)** | `doc`, `xls`, `ppt` |
| **OpenDocument** | `odt`, `ods`, `odp`, `odg` |
| **Text & data** | `txt`, `rtf`, `csv`, `xml`, `json` |
| **Web** | `html`, `htm`, `mhtml` |
| **Email** | `eml`, `msg` |
| **CAD** | `dwg`, `dxf` |
| **XPS** | `xps` |

> **PDF, images, text, HTML, and data files** print and convert with no extra software.
> **Office, OpenDocument, email, CAD, and XPS** use **LibreOffice**, which the self-contained
> Windows installer bundles automatically (no separate install or admin rights needed).

---

## How it works (under the hood)

- **Printing** — on Windows via `pdf-to-printer` (bundled SumatraPDF); on macOS/Linux via `lp`.
- **Office / CAD / email conversion** — LibreOffice in headless mode (bundled or auto-detected).
- **Images** — processed with `sharp`.
- **HTML → PDF** — rendered by Electron's built-in engine.
- **PDF text / OCR** — `pdf.js` for text extraction, `Tesseract.js` for offline OCR.
- **Billing data** — stored in plain JSON files in the app's user-data folder (zero extra dependencies, survives updates).
- **Self-contained installer** — bundles LibreOffice (plus the MSVC runtime it needs), the OCR engine, and the print component, so it runs on a clean machine with no admin rights.

Built with **Electron + React** (electron-vite), packaged with **electron-builder**.

---

## Platforms

- **Windows 10+** — primary, self-contained installer (per-user, no admin).
- **macOS** — supported; `.dmg` is built on a Mac. See [INSTALLATION.md](INSTALLATION.md#macos).
- **Linux** — AppImage / snap builds available from source (see [BUILD.md](../BUILD.md)).

---

© 2026 Radixile Technology Solutions LLP, Pune, India.
