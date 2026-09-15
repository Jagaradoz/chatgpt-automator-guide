# Troubleshooting & Frequently Asked Questions

Find solutions to common issues when using **ChatGPT Automator**.

---

## 1. Frequently Asked Questions

### Q: Does this require an OpenAI API Key?
**No.** ChatGPT Automator automates your regular browser session at `https://chatgpt.com/`. It runs on whatever subscription tier you currently have logged in (Free, Plus, Team, or Enterprise).

### Q: Does it send my prompts or personal data to third-party servers?
**Most queue data stays in your browser**, but a few optional paths leave the machine:

| What | Where it goes |
|---|---|
| Prompts + attachments when you press **Start** | Your logged-in ChatGPT / OpenAI session (by design) |
| Drafts, settings, queue snapshot | Chrome extension storage on your device |
| Optional **Pro** checkout / license | ExtensionPay and Stripe |
| Optional **Report bugs** submission | Developer Google Apps Script endpoint (only if you submit) |

There is no advertising tracker or analytics SDK in the extension. See the [Privacy Policy](../PRIVACY_POLICY.md) for full detail.

### Q: What is Free vs Pro on the badge?
**Free / Pro** refers to the **extension** license (optional one-time Pro unlock), not your ChatGPT subscription. Core queue features work on Free. Details: [Pro, Languages & Support](06-pro-languages-and-support.md).

### Q: Can I change the UI language?
Yes. Use the globe control in the side-panel header. Supported languages are listed in [Pro, Languages & Support](06-pro-languages-and-support.md).

### Q: Can I close the side panel while a queue is running?
Yes. Queue state and completed answers are kept in extension storage for the browser session. Reopening the side panel restores progress and controls. Image attachments are not snapshotted—you may need to reattach them after a full restart.

### Q: Can I run prompts in new chat conversations each time?
Yes. In Settings, enable **Start Each Job in a New Conversation** if you want each prompt isolated from prior context.

### Q: How do I report a bug?
Prefer **⋯ → Report bugs** in the side panel for product issues. You can also open a GitHub issue with the [bug report template](../.github/ISSUE_TEMPLATE/bug_report.md). More detail: [Pro, Languages & Support](06-pro-languages-and-support.md).

---

## 2. Common Issues & Solutions

### Issue: "ChatGPT tab not detected" or "Tab disconnected"
- **Cause**: The side panel could not locate an active tab with `chatgpt.com` open.
- **Solution**:
  1. Open a new tab and go to `https://chatgpt.com/`.
  2. Ensure you are signed in.
  3. Re-open or refresh the side panel.

### Issue: Prompts fail with "Editor element not found"
- **Cause**: OpenAI periodically updates class names and DOM structures on `chatgpt.com`.
- **Solution**:
  1. Make sure your extension is updated to the latest release version.
  2. Refresh your ChatGPT browser tab (`Ctrl+R` or `Cmd+R`).
  3. If the problem persists after an OpenAI website overhaul, check the [Issue Tracker](https://github.com/Jagaradoz/chatgpt-automator-guide/issues) for an update notice.

### Issue: "3 Consecutive Failures – Queue Stopped"
- **Cause**: The safety mechanism stopped the run to prevent wasting your queue.
- **Solution**:
  1. Check the pinned ChatGPT tab. Did a CAPTCHA challenge or Cloudflare verification appear?
  2. Did you hit a temporary ChatGPT model rate limit?
  3. Once you clear the verification or cooldown, click **Retry Failed** to continue where you left off.

### Issue: Images are not downloading automatically
- **Cause**: Chrome download permissions may be blocked, or the setting is toggled off.
- **Solution**:
  1. In the side panel Options / Settings, verify auto-download for generated images (or text) is enabled.
  2. Check Chrome's download bar or browser permissions so Chrome may save files automatically.

### Issue: Pro purchase succeeded but badge still says Free
- **Cause**: License cache not refreshed yet, or the ExtensionPay page was closed early.
- **Solution**:
  1. Re-open the panel or click the Free/Pro badge again.
  2. Confirm you completed checkout in the ExtensionPay window.
  3. If it still fails, use **Report bugs** with the approximate purchase time (do not include card details).

---

## Still have questions?

- In-app: **⋯ → Report bugs**
- GitHub: [Issues](https://github.com/Jagaradoz/chatgpt-automator-guide/issues)
