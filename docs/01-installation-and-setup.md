# Installation & Getting Started

This guide explains how to install and set up **ChatGPT Automator** in Google Chrome.

---

## 1. Installation Options

### Option A: From the Chrome Web Store (Recommended)

1. Open the ChatGPT Automator page on the [Chrome Web Store](https://chrome.google.com/webstore) (search for **ChatGPT Automator** if the direct listing link is not live yet).
2. Click **Add to Chrome**.
3. Confirm the prompt to grant permissions.

> [!NOTE]
> After the store listing is published, this guide will be updated with the permanent item URL.

### Option B: Load as Unpacked Extension (Developer / ZIP Release)

If you have downloaded a release `.zip` or built the project from source:

1. Unzip the downloaded file (ensure you have the folder containing `manifest.json`).
2. Open Google Chrome and navigate to:
   ```text
   chrome://extensions
   ```
3. In the top-right corner, turn on **Developer mode**.
4. Click the **Load unpacked** button in the top-left corner.
5. Select the unpacked extension folder (e.g. `dist/` or the unzipped package root).
6. You should now see **ChatGPT Automator** active in your extension list.

---

## 2. Opening the Side Panel

1. Click the **Extensions** (puzzle piece) icon in Chrome's top toolbar.
2. Find **ChatGPT Automator** and click the **Pin** icon to keep it accessible.
3. Click the extension icon. The side panel will open on the right side of your browser.

> [!TIP]
> You can also right-click the extension icon and select **Open Side Panel**.

### Header controls worth knowing

- **Globe** — change UI language
- **⋯ menu** — How to use, Settings, Report bugs (and version)
- **Free / Pro badge** — license status and upgrade entry

More detail: [Pro, Languages & Support](06-pro-languages-and-support.md).

---

## 3. Pinned Tab Workflow

To keep your automated runs safe and prevent accidental prompt submission to incorrect pages, ChatGPT Automator **pins to one active ChatGPT tab**:

1. Open `https://chatgpt.com/` in a Chrome tab and make sure you are logged in.
2. Open the ChatGPT Automator side panel.
3. The panel automatically detects the active ChatGPT tab and connects to it.
4. **Tab Isolation**: Even if you switch tabs or browse other websites in other windows, the automation stays locked onto that specific ChatGPT tab.
5. If you close the ChatGPT tab, the automation will immediately pause or stop to protect the queue from executing into a void.

---

## Next Steps

- Check out [Prompt Modes & Features](02-modes-and-features.md) to learn how to run text and image queues.
- Read [Safe Pacing & Rate Limits](04-safe-pacing-and-limits.md) to configure delays properly before your first large batch.
- Skim [Pro, Languages & Support](06-pro-languages-and-support.md) for languages, Pro, and bug reporting.
