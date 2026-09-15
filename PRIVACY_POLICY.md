# Privacy Policy for ChatGPT Automator

*Last updated: September 15, 2026*

ChatGPT Automator is a browser extension that submits user-selected batches of prompts and optional images through the user's existing ChatGPT web session. It is an independent product and is not affiliated with or endorsed by OpenAI.

## 1. Data the extension handles

- **Prompts and imported prompt files:** Draft prompt text is stored in `chrome.storage.local` so it can be restored when the panel reopens.
- **Queue state and results:** The active queue, statuses, captured assistant text, and generated-image URLs are stored temporarily in `chrome.storage.session` for recovery while the browser session remains active.
- **Attachments:** Selected images are read into extension memory so they can be attached to ChatGPT. Image bytes are deliberately excluded from stored queue snapshots; users must reattach them after the panel closes.
- **Settings:** Delay, mode, download, appearance, UI language, and other preferences are stored in `chrome.storage.local`.
- **License state:** A cached paid/free flag is stored locally. ExtensionPay may also store an installation identifier and license information using Chrome extension storage.
- **Optional bug reports:** If the user submits feedback through **Report bugs**, the extension sends the description the user typed, an optional reply email, the active mode, and non-sensitive diagnostics (extension version, platform, browser language, user agent, and panel window size). Prompt drafts, queue contents, attachments, ChatGPT conversation text, and account credentials are not included unless the user pastes them into the description themselves.

## 2. External processing

When the user starts a queue, the extension intentionally inserts prompts and selected attachments into ChatGPT. That content is therefore transmitted to and processed by OpenAI through the user's logged-in ChatGPT session, subject to OpenAI's terms and privacy practices. The extension does not read or store OpenAI passwords, session cookies, or payment credentials.

If the user opens the Pro purchase or account page, ExtensionPay and its payment provider Stripe process the information necessary to provide checkout and license validation. This can include an installation identifier, email address, license status, and payment details. Prompt and response content is not sent to ExtensionPay.

If the user voluntarily submits a bug report, the report payload is posted to a Google Apps Script web app operated by the developer (`script.google.com` / `script.googleusercontent.com`) so the developer can investigate and reply. That payload is used only for support and product improvement. Do not include secrets or personal data you do not want the developer to receive.

The extension contains no developer-operated analytics, advertising trackers, or telemetry service. The developer does not sell user data.

## 3. Downloads

If automatic downloads are enabled, Chrome's Downloads API saves captured text or generated images to the user's Downloads folder. Generated-image URLs originate from ChatGPT/OpenAI. Files are not routed through a developer-operated server.

## 4. Chrome permissions

| Permission or site access | Purpose |
| --- | --- |
| `sidePanel` | Displays the queue and controls in Chrome's side panel. |
| `tabs` | Selects and pins a ChatGPT tab for a run and observes navigation/reload state. |
| `scripting` | Restores the bundled content script when a permitted ChatGPT page has not loaded it. |
| `storage` | Stores settings, draft text, temporary queue state, and cached license state. |
| `downloads` | Saves user-requested text and image output locally. |
| `chatgpt.com` and `chat.openai.com` | Inserts prompts, attaches images, observes completion, and captures requested output. |
| `script.google.com` and `script.googleusercontent.com` | Delivers optional user-submitted bug reports to the developer's Google Apps Script endpoint. |
| `extensionpay.com` (content script) | Enables ExtensionPay payment-completion callbacks for optional Pro licensing. |

## 5. Retention and control

The panel's Clear action removes the current draft, attachments, and queue snapshot; it does not reset preferences or ExtensionPay license state. Settings and UI language can be changed in the panel. Uninstalling the extension removes its Chrome-managed local and session storage. Data already submitted to ChatGPT, ExtensionPay, or an optional bug-report endpoint is controlled through those services or by contacting the developer for support requests.

## 6. Contact

Questions or privacy requests can be submitted through the in-extension **Report bugs** form, the project's GitHub issue tracker, or the developer support channel at https://github.com/Jagaradoz.
