# Pro, Languages & Support

Extras in ChatGPT Automator beyond the core queue: optional Pro licensing, UI languages, and how to get help.

---

## 1. Free vs Pro

ChatGPT Automator is free to install. Optional **Pro** unlocks premium extras (for example desktop pet themes) via a one-time purchase.

| | Free | Pro |
|---|---|---|
| Prompt queue (text + image modes) | Yes | Yes |
| Import / export / pacing / auto-download | Yes | Yes |
| Premium desktop pets and related Pro UI | No | Yes |

### How to upgrade

1. Open the side panel.
2. Click the **Free** / **Pro** badge near the title (or open **Settings**).
3. Follow the ExtensionPay checkout flow.

Payments and license validation are handled by **ExtensionPay** and **Stripe**. Prompt text, attachments, and ChatGPT responses are **not** sent to ExtensionPay.

> [!NOTE]
> Your ChatGPT plan (Free / Plus / Team / Enterprise) is separate from the extension’s Free / Pro badge. The extension uses whatever ChatGPT account you are already signed into in the browser.

---

## 2. UI languages

Use the **globe** button in the side-panel header to change the interface language. Your choice is saved in extension settings.

Currently supported:

- English
- Indonesian (Bahasa Indonesia)
- Thai
- Vietnamese
- Simplified Chinese

Prompt content you type or import is **not** auto-translated—only the panel UI labels change.

---

## 3. In-app How to use

The header **⋯** menu includes **How to use**—a short five-step overview inside the panel.

For deeper docs, pacing tables, and import templates, stay in this repository.

---

## 4. Report a bug or send feedback

### From the extension (recommended for product bugs)

1. Open the side panel.
2. Open the **⋯** menu → **Report bugs**.
3. Enter a description (required) and optionally an email if you want a reply.
4. Submit.

That sends your message, optional email, active mode, and non-sensitive diagnostics (extension version, platform, browser language, user agent, panel size) to the developer’s Google Apps Script endpoint. It does **not** automatically attach your prompt queue, images, or ChatGPT conversation—unless you paste them into the description yourself.

### From GitHub

- Product / selector issues: [Bug report template](../.github/ISSUE_TEMPLATE/bug_report.md)
- New cookbook templates: [Template request](../.github/ISSUE_TEMPLATE/template_request.md)

---

## Next Steps

- Return to [Installation & Setup](01-installation-and-setup.md) if you are still getting started.
- See [Troubleshooting & FAQ](05-troubleshooting-and-faq.md) for common failures and privacy details.
