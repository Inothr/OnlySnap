# OnlySnap

> Fork of [jordon31/OnlySnap](https://github.com/jordon31/OnlySnap) with automated login and dependency management.

A **TUI** (Terminal User Interface) tool for OnlyFans content downloading. No command-line knowledge needed, just click and download.

## What's changed from the original

- **Automated login:** Replaced manual cookie extraction (F12, DevTools, copy-paste headers) with an automated Chrome login window.
- **Isolated Chrome instance:** The login opens a separate Chrome profile that doesn't touch the user's personal browser data.
- **Automatic dependency detection:** The app checks for missing tools (N_m3u8DL-RE, mp4decrypt, ffmpeg) on startup and offers to download and install them automatically.
- **Removed `cookie-onlyfans.py`:** No longer needed since login is handled automatically.

---

## Requirements

- **Python 3.10+**
- **Google Chrome** installed (required for the automated login)
- **Pillow** (included in `requirements.txt`, required for watermarks)
- Install dependencies: `pip install -r requirements.txt`

### Platform support

| Platform | Status |
| --- | --- |
| **Linux** | ✅ Tested |
| **Windows** | ⚠️ Should work, not fully tested yet |
| **macOS** | ⚠️ Should work, not fully tested yet |

---

## HOW TO START

1. Run `!run.bat` (Windows) or `python OnlySnap.py` (Linux/Mac)

### THE LAUNCHER

Inside `!run.bat`:

* **[1] START ONLYSNAP** — Opens the main app.
* **[2] INSTALL DRM TOOLS** — Downloads FFmpeg, mp4decrypt and N_m3u8DL-RE into the `dmr` folder.

---

## 🔐 AUTOMATED LOGIN

No more manual cookie extraction. Here's how it works:

1. Click the **Login** button inside the app.
2. An isolated Chrome window opens (separate from your personal browser).
3. Log in to OnlyFans normally from that window.
4. Once logged in, the app captures the cookies automatically in the background.
5. The Chrome window closes and the session is saved. Ready to use.

If a saved session already exists, the app asks if you want to replace it with a new one.

🎥 **Login Demo:** 





https://github.com/user-attachments/assets/7f336ee4-343f-4278-a657-f6703e664abb





## 🔧 AUTOMATIC DEPENDENCY INSTALLATION

On startup, the app checks if the following tools are present:

| Tool | What it does |
| --- | --- |
| **N_m3u8DL-RE** | Downloads encrypted video streams |
| **mp4decrypt** | Decrypts DRM-protected media |
| **ffmpeg** | Media processing and conversion |

If any are missing, a screen appears offering to download and install them automatically into the `dmr` folder. Downloads are pulled directly from the official sources for each platform.

---

## ⚙️ SETTINGS

Settings are managed directly from the app using the **[SETTINGS]** button. No need to manually edit `Config.json`. All changes are **auto-saved in real-time**.

| Setting | Description |
| --- | --- |
| **Custom Filename** | Add a prefix to filenames. Leave empty for original IDs. |
| **Watermark Text** | Adds a dynamic watermark on every photo. |
| **Month Names** | `true` = month names, `false` = numbers. |
| **No Year Folders** | `true` = all files in one folder. |
| **Skip Highlights Covers** | Skips highlight cover images. |
| **Disable Text Files** | `true` = only media, `false` = includes `.txt` with post caption. |
| **Download Tagged** | Downloads SPAM/AD posts. Default `false`. |
| **Workers (Threads)** | Download speed. Default is 5. |

---

## ⚠️ FILENAME LOGIC

The script checks if a file exists by its **name**. If a **Custom Filename Prefix** is set and later removed, files will be re-downloaded because the expected filename changes.

---

## 📸 SMART WATERMARK

Automatic watermark system for photos with dynamic sizing based on resolution. White text with subtle shadow on a semi-transparent background. Custom `.ttf` fonts can be placed in the main folder.

---

## 🔧 EXTRAS

* **Telegram:** [https://t.me/OnlySnap0](https://t.me/OnlySnap0)
* **Bugs / Suggestions:** Open an issue.
* **Disclaimer:** For educational purposes only.

OnlyFans Scrape - Scrape OnlyFans
