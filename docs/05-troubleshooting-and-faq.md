# ❓ Troubleshooting & Frequently Asked Questions

Find solutions to common issues when using **ChatGPT Automator**.

---

## 1. Frequently Asked Questions

### Q: Does this require an OpenAI API Key?
**No.** ChatGPT Automator automates your regular browser session at `https://chatgpt.com/`. It runs on whatever subscription tier you currently have logged in (Free, Plus, Team, or Enterprise).

### Q: Does it send my prompts or personal data to third-party servers?
**No.** ChatGPT Automator operates 100% locally on your machine. Your prompts, images, queue progress, and outputs stay strictly inside Chrome's local storage and your browser tab.

### Q: Can I close the side panel while a queue is running?
Yes. Your queue state, drafted inputs, and completed answers are continuously saved in `chrome.storage.local`. Reopening the side panel will restore your active progress and queue controls.

### Q: Can I run prompts in new chat conversations each time?
Yes! In the settings menu, toggle on **Start Each Job in a New Conversation** if you want each prompt isolated from prior context.

---

## 2. Common Issues & Solutions

### ❌ Issue: "ChatGPT tab not detected" or "Tab disconnected"
- **Cause**: The side panel could not locate an active tab with `chatgpt.com` open.
- **Solution**:
  1. Open a new tab and go to `https://chatgpt.com/`.
  2. Ensure you are signed in.
  3. Re-open or refresh the side panel.

### ❌ Issue: Prompts fail with "Editor element not found"
- **Cause**: OpenAI periodically updates class names and DOM structures on `chatgpt.com`.
- **Solution**:
  1. Make sure your extension is updated to the latest release version.
  2. Refresh your ChatGPT browser tab (`Ctrl+R` or `Cmd+R`).
  3. If the problem persists after an OpenAI website overhaul, submit a report via the in-app **Report an Issue** menu in the extension side panel.

### ❌ Issue: "3 Consecutive Failures – Queue Stopped"
- **Cause**: The safety mechanism stopped the run to prevent wasting your queue.
- **Solution**:
  1. Check the pinned ChatGPT tab. Did a CAPTCHA challenge or Cloudflare verification appear?
  2. Did you hit a temporary ChatGPT model rate limit?
  3. Once you clear the verification or cooldown, click **Retry Failed** to continue where you left off.

### ❌ Issue: Images are not downloading automatically
- **Cause**: Chrome download permissions may be blocked, or the setting is toggled off.
- **Solution**:
  1. In the side panel settings, verify **Auto-Download Generated Images** is enabled.
  2. Check Chrome's download bar or browser permissions to make sure Chrome is permitted to save files automatically.

---

## Still need help?
Open the side panel menu in the extension and select **Report an Issue** to send your feedback directly to the developer.
