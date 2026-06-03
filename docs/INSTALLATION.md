# Installation Guide — Radixile PrintPool

This guide walks you through installing **PrintPool** on Windows, step by step.
No technical knowledge is needed. Most users will be printing within a couple of minutes.

> Published by **Radixile Technology Solutions LLP**, Pune, MH, India.

---

## 1. System requirements

| | |
|---|---|
| **Operating system** | Windows 10 or newer (64-bit). macOS is also supported — see the [macOS](#macos) note below. |
| **Free disk space** | About **1 GB** (the installer is self-contained and bundles everything it needs). |
| **Admin rights** | **Not required.** PrintPool installs just for your user account. |
| **Internet** | Not required to install or run — everything works offline once installed. |

---

## 2. Download the installer

1. Open the **[GitHub Releases page](https://github.com/share2abhishek/Printpool/releases/latest)**.
2. Under **Assets**, download:

   ```
   printpool-<version>-setup.exe
   ```

   *(`<version>` is the latest version number, e.g. `printpool-1.0.0-setup.exe`.)*

The download is **open to everyone** — no account, sign-in, or licence key is required.

---

## 3. Run the installer

1. Double-click the downloaded `printpool-<version>-setup.exe`.
2. The app installs to your user folder (`%LOCALAPPDATA%\Programs\PrintPool`). You will **not**
   be asked for an administrator password.
3. When it finishes, PrintPool opens automatically. A shortcut is added to your Start menu.

### "Windows protected your PC" message

The first time you run the installer, Windows **SmartScreen** may show a blue
**"Windows protected your PC"** dialog. This is normal for newly published apps that are not
yet code-signed — it is **not** a virus warning.

To continue:

1. Click **More info**.
2. Click **Run anyway**.

*(A `SMARTSCREEN.txt` file is bundled with the app explaining this same step.)*

---

## 4. First launch checklist

After PrintPool opens for the first time:

1. **Pick a printer** — go to the **Printers** tab and click your printer. The choice is saved.
   If you skip this, PrintPool uses your Windows default printer.
2. **(Optional) Office files** — to print or convert **Word, Excel, PowerPoint, OpenDocument,
   email, or CAD** files, PrintPool uses LibreOffice. The self-contained installer **already
   bundles LibreOffice**, so this works out of the box. You can confirm under
   **Settings → LibreOffice → Status** — it should show ✅ and a version number.
3. **Print a test** — add a PDF on the **Files** tab and click the green **Print All** button.

You're ready. See the **[Help / User Guide](HELP.md)** for everything else.

---

## 5. Upgrading to a newer version

1. Download the newer `printpool-<version>-setup.exe` from the Releases page.
2. Run it. It replaces your existing installation automatically.
3. If PrintPool is open, the installer asks you to **close it first** — close it and continue.

Your saved printer, settings, and print history are kept across upgrades.

---

## 6. Uninstalling

1. Open Windows **Settings → Apps → Installed apps** (or **Add or remove programs**).
2. Find **Radixile PrintPool**, click **⋯ → Uninstall**.

Because PrintPool installs per-user, no administrator password is needed to remove it.

---

## 7. Troubleshooting installation

| Problem | What to do |
|---------|-----------|
| **SmartScreen won't let me run it** | Click **More info → Run anyway** (see [above](#windows-protected-your-pc-message)). |
| **"Not enough disk space"** | The installer needs ~1 GB free on the install drive. Free up space and retry. |
| **"This app can't run on your PC" / version error** | PrintPool needs Windows 10 or newer (64-bit). |
| **Installer says PrintPool is already running** | Close PrintPool (also check the system tray near the clock) and click Retry. |
| **Office files won't print after install** | Open **Settings → LibreOffice → Status**. If it isn't ✅, see the [Help guide](HELP.md#something-went-wrong). |
| **Antivirus quarantined the file** | The build is unsigned, which some antivirus tools flag. Restore the file or add an exception, then re-run. |

---

## macOS

A macOS build (`.dmg`) is available where published. Open the `.dmg`, drag **PrintPool** into
your **Applications** folder, then launch it. On first run, right-click the app and choose
**Open** to bypass Gatekeeper for the unsigned build. LibreOffice is used for Office-format
support on macOS as well.

---

## Building from source

Developers can build their own installer instead of downloading one — see **[BUILD.md](../BUILD.md)**.

---

Need help using the app once it's installed? See the **[User Guide](HELP.md)**.
For the full feature list, see **[FEATURES.md](FEATURES.md)**.
