# Changelog

All notable changes to **Radixile PrintPool** are documented here.
This project follows [Semantic Versioning](https://semver.org/) (`MAJOR.MINOR.PATCH`) and
the [Keep a Changelog](https://keepachangelog.com/) format. The version in `package.json`
drives the installer name and the executable's version resource.

## [1.0.0] — 2026-06-03

First public release.

### Added
- **Batch printing** — add many documents, reorder, and print them all to a chosen printer.
- **Printer selection** — pick a printer in the Printers tab; the choice is persisted and
  falls back to the system default. Clear message when no printer is configured.
- **Print to PDF** — "Microsoft Print to PDF" / XPS prompt for a file name + location
  (Save As) and write the generated PDF.
- **Reprint** — reprint from History, single row or multi-select ("Reprint selected").
- **Document conversion** — convert PDF / Office / OpenDocument / images between formats.
- **PDF → Word/text (OCR)** — extract a PDF's text layer when present; OCR scanned pages
  offline with bundled Tesseract.js (English, Hindi, Spanish, French; selectable in Settings).
- **Conversion validation** — the Convert screen only offers targets that actually work
  for the selected files.
- **Preview** — view queued PDFs before printing.
- **Schedule & watch-folder** — recurring prints and auto-print of files dropped in a folder.
- **Print history** — full log with CSV export.
- **Self-contained Windows installer** — bundles LibreOffice + the MSVC runtime DLLs it
  needs + the offline OCR engine + the printing component (SumatraPDF), so it works on a
  clean machine with no admin rights.
- **Hardened installer** — per-user (no UAC), Windows-version and disk-space prechecks,
  SmartScreen guidance, and a runtime LibreOffice self-test in Settings.
- **Branding** — app logo/icon; company name shown in the status bar and the executable
  metadata (`Radixile Technology Solutions LLP | Pune | MH | INDIA`).
- **UI** — panel transition animations, processing spinners, hover feedback.

### Fixed
- Printing in the installed app (the print component is now unpacked from the asar).
- Print All now prints all queued items (no more "0 files" after a prior run).
- Preview now renders queued PDFs (corrected a malformed `file://` URL on Windows).
- History row layout and unreadable button/printer-name text.
- Installer now upgrades cleanly over a previous version (closes the running app first).

[1.0.0]: https://bitbucket.org/radixile/printpool/downloads/
