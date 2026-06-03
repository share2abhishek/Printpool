# Building PrintPool installers

PrintPool is built with `electron-vite` + `electron-builder`.

```bash
npm install
npm run build:win     # Windows NSIS installer
npm run build:mac     # macOS DMG
npm run build:linux   # Linux AppImage + snap
```

Output goes to `dist/`.

## LibreOffice (Office / Word / Excel / PowerPoint / CAD support)

PrintPool needs LibreOffice to print or convert Office, OpenDocument, email,
and CAD files. PDF, images, text, and HTML work without it.

At runtime PrintPool looks for LibreOffice in this order:

1. The path set in **Settings → LibreOffice location**
2. Standard install locations for the OS
3. A copy bundled inside the app (`resources/libreoffice/`)

So there are two ways to ship:

### Option A — Lean installer (default)

```bash
npm run build:win
```

LibreOffice is **not** bundled (~smaller installer). End users who already have
LibreOffice get full functionality automatically; those who don't see a
friendly "Install LibreOffice" prompt for Office formats.

### Option B — Fully self-contained installer (recommended for distribution)

```bash
npm run build:win:bundle
```

This single command stages LibreOffice into `resources/libreoffice/`, copies the
MSVC runtime DLLs LibreOffice needs next to `soffice.exe` (so **no Visual C++
Redistributable and no admin rights are required on the target machine**), and
builds the NSIS installer (~400 MB) at `dist/printpool-<version>-setup.exe`.

To point at a specific LibreOffice install instead of auto-detecting:

```bash
set PRINTPOOL_LIBREOFFICE_SRC=C:\PortableApps\LibreOffice  &&  npm run build:win:bundle
```

The staged binaries are never committed to git (`resources/libreoffice/**` is
ignored); they are copied in fresh at build time.

#### What the installer handles

The installer is per-user (installs to AppData, never prompts for admin/UAC) and
runs these prechecks with clear messages:

- **Windows version** — requires Windows 10+; aborts with a message otherwise.
- **Disk space** — requires ≥ 1 GB free on the install drive; aborts otherwise.
- **App already running** — prompts the user to close PrintPool before upgrading.
- **Unsigned-app warning** — bundled `SMARTSCREEN.txt` explains the SmartScreen
  "More info → Run anyway" step (the build is not code-signed).

On first launch the app self-tests LibreOffice (Settings → LibreOffice → Status)
and shows an actionable message if it cannot start.

#### Manual install verification checklist

1. Copy the `.exe` to a clean Windows 10/11 VM with **no LibreOffice** and **no VC++ runtime**.
2. Run it — confirm no UAC/admin prompt; it installs to `%LOCALAPPDATA%\Programs\PrintPool`.
3. Launch PrintPool → Settings → LibreOffice → Status shows `✅ <version>`.
4. Convert a `.docx` to PDF — confirm it succeeds.
5. Re-run the installer while the app is open — confirm the "close the app" prompt appears.

## OCR (PDF → Word / editable text)

PrintPool recovers text from PDFs to produce DOCX/ODT/RTF/TXT:
- PDFs with a real text layer are read directly (instant, accurate).
- Scanned/image PDFs are OCR'd with bundled Tesseract.js (offline).

`npm run prebuild` (run automatically by every build) stages the OCR runtime
into `resources/ocr/` via `scripts/stage-ocr-assets.js`:
- pdf.js + Tesseract.js engine into `resources/ocr/lib/`
- language data into `resources/ocr/lang/` (downloaded once; cached). Override
  the set with `PRINTPOOL_OCR_LANGS=eng,hin,...` before building.

These are git-ignored and copied fresh at build time, then shipped via
`extraResources`/`asarUnpack`. OCR needs internet only at **build** time to
fetch language data; the installed app is fully offline. The active OCR
language is chosen in Settings → OCR.

## Printing

- Choose the printer in the **Printers** tab (click a printer — the choice is saved).
  Print All and Reprint use it; without a selection PrintPool falls back to the
  system default printer, and shows a clear message if neither is set.
- **Microsoft Print to PDF / XPS**: PrintPool saves the generated PDF to a folder
  you pick (no per-file Windows save dialog).
- **Reprint**: the **History** tab supports selecting rows (checkboxes + "select all
  shown") and a **Reprint selected** button, plus a per-row **Reprint**.
- The installed app bundles SumatraPDF (via `pdf-to-printer`), unpacked from the
  asar so it can execute — required for printing to work in the packaged build.

## Platform note (Windows vs macOS)

- **Windows** builds run on Windows (this repo is developed there): `npm run build:win:bundle`.
- **macOS** builds (`.dmg`) **must be produced on a Mac** — electron-builder cannot
  cross-compile/sign a macOS app from Windows or Linux. On a Mac with LibreOffice
  installed, run `npm run build:mac:bundle` for a self-contained DMG, or
  `npm run build:mac` for the lean build. `build/entitlements.mac.plist` is included
  for the hardened runtime. CI (a macOS runner) is the usual way to produce both
  installers from one pipeline.
