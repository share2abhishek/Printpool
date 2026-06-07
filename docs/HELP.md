# User Guide / Help — Radixile PrintPool

Everything you need, in plain English. **PrintPool prints many documents at once** — add your
files, click **Print All**, and PrintPool handles the rest, with no need to open each program
one by one.

> This is the same help available inside the app on the **Help** (❓) tab.
> New here? Start with the [Installation Guide](INSTALLATION.md).

---

## Contents

- [Getting started in 3 steps](#getting-started-in-3-steps)
- [Adding documents](#adding-documents)
- [Changing the print order](#changing-the-print-order)
- [Copies, pages, and double-sided](#copies-pages-and-double-sided)
- [What "Print Mode" means](#what-print-mode-means)
- [Printing to PDF](#printing-to-pdf)
- [Converting files to another format](#converting-files-to-another-format)
- [PDF → Word (OCR)](#pdf--word-ocr)
- [Printing automatically at a set time](#printing-automatically-at-a-set-time)
- [Auto-print files dropped in a folder](#auto-print-files-dropped-in-a-folder)
- [Saving a list to reuse later](#saving-a-list-to-reuse-later)
- [Print history & reprinting](#print-history--reprinting)
- [🆕 Generating a client bill (Billing)](#-generating-a-client-bill-billing)
- [🆕 Client book (Clients)](#-client-book-clients)
- [🆕 Sales reports (Reports)](#-sales-reports-reports)
- [Settings](#settings)
- [Something went wrong?](#something-went-wrong)

---

## Getting started in 3 steps

1. Go to the **Files** page and add the documents you want to print — drag them onto the
   window, or click **+ Add Files**.
2. Pick your printer on the **Printers** page (the one marked **Default** is used automatically).
3. Click the green **Print All** button on the left. PrintPool prints every document in the
   list, one after another.

---

## Adding documents

There are two easy ways:

- **Drag and drop** — select files in Windows File Explorer and drag them onto the PrintPool window.
- **Add Files button** — click **+ Add Files** on the Files page and choose documents.

You can add many files at once. PrintPool supports PDFs, Word, Excel, PowerPoint, images, and
**35+ file types** — see the full list in [FEATURES.md](FEATURES.md#supported-file-formats).
You don't need to open each program yourself.

---

## Changing the print order

In the Files list, **drag a document up or down** to change when it prints. Documents print from
**top to bottom**. To remove one, click the **✕** button next to it.

---

## Copies, pages, and double-sided

Click the **gear (⚙️)** icon next to any document to open its print settings. You can set:

- **Copies** — how many times to print it.
- **Pages** — print everything (`all`) or just some pages (for example `1-3,5`).
- **Print Both Sides** — single-sided or double-sided (duplex).
- **Orientation** — portrait or landscape.
- **Paper Size** — A4, Letter, and more.

**Each document can have its own settings.**

---

## What "Print Mode" means

Most people can leave this on **Automatic** — PrintPool picks the best option for you.

If you want to choose:

- **Direct** — prints the file using the program it normally opens in (like Word). Fastest, and
  looks exactly like the original.
- **Via PDF** — converts the file to a PDF first, then prints. Useful when the original program
  isn't installed, or when you need exact control over copies and double-sided printing.

---

## Printing to PDF

To save documents as PDF instead of printing on paper:

1. On the **Printers** tab, select **"Microsoft Print to PDF"**.
2. Click **Print All**.
3. PrintPool asks for a **file name + location** (Save As) for each document and writes the PDF there.

---

## Converting files to another format

Open the **Convert** page to change a file into another format and save it — **without printing**.

1. Choose one or more files.
2. Pick the format to convert to (PDF, Word, Excel, PowerPoint, OpenDocument, or image formats
   like PNG / JPG / WebP).
3. Choose where to save them (or leave blank to save next to the originals).
4. Click **Convert**.

The Convert screen only offers target formats that actually work for the files you selected.
Converting Office documents uses LibreOffice (bundled with the installer). Image and HTML
conversions work without anything extra.

---

## PDF → Word (OCR)

In **Convert**, choose a PDF and target **Word (DOCX)**, ODT, RTF, or TXT:

- PDFs with a real **text layer** convert instantly and accurately.
- **Scanned / image-only** PDFs are read with built-in OCR, fully **offline**.

Set the OCR language under **Settings → OCR** — English, Hindi, Spanish, or French.

---

## Printing automatically at a set time

Open the **Schedule** page to have PrintPool print your list automatically:

- **One time** — pick a date and time.
- **Every day** or **Every week** — pick the time (and the days, for weekly).

Keep PrintPool running (it can sit quietly in the system tray) and it prints on schedule without
you doing anything.

---

## Auto-print files dropped in a folder

On the **Settings** page you can choose a **Watch Folder**. After that, any new file you save into
that folder is added to PrintPool and printed automatically. Great for scanned documents or
reports that arrive regularly.

---

## Saving a list to reuse later

If you print the same set of documents regularly (like weekly reports), you can **save the whole
list** as a file and load it again later — all your per-document settings are remembered.

---

## Print history & reprinting

The **History** page keeps a record of every document you printed — when, on which printer, and
whether it succeeded. From here you can:

- **Filter** to show only errors.
- **Reprint** a single row, or tick several rows (or "select all shown") and **Reprint selected**.
- **Export** the whole list to a spreadsheet (**CSV**) for a report.

---

## Settings

The **Settings** page controls:

- **Default print mode** — Automatic, Direct, or Via PDF for new documents.
- **LibreOffice location** — auto-detected; shows a ✅ status when it's working.
- **OCR language** — the language used when reading scanned PDFs.
- **Watch Folder** — the folder to auto-print from (see above).
- **Minimise to tray** — keep PrintPool running quietly in the background.

---

## Something went wrong?

PrintPool always tells you what happened in plain English, right next to the document. Common
situations:

- **"Printer is offline"** — check the printer is turned on and connected, then click **Retry**.
- **"LibreOffice is required"** — to print Word / Excel / PowerPoint files, LibreOffice must be
  available. The self-contained installer bundles it; if you used a lean build, install the free
  [LibreOffice](https://www.libreoffice.org/) and reopen PrintPool. Check
  **Settings → LibreOffice → Status**.
- **"File could not be found"** — the file was moved or deleted; remove it from the list and add
  it again.
- A **red error on one file never stops the others** — PrintPool skips it and keeps printing the
  rest, then shows you a summary.

Still stuck? Check the **History** page to see the exact message for any document that didn't
print.
