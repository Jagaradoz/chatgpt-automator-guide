# ⏱️ Safe Pacing, Rate Limits & Compliance

Because **ChatGPT Automator** operates directly on the ChatGPT Web UI (`https://chatgpt.com/`), understanding pacing and web platform safeguards is critical for a smooth automation experience.

---

## 1. Why Natural Pacing Matters

Unlike the commercial OpenAI API (which charges per token and handles programmatic requests), the ChatGPT web application is designed for interactive human sessions. 

Sending rapid bursts of consecutive prompts without delays can trigger:
1. Temporary usage cooldowns (e.g., *"You've reached your current usage cap"*).
2. Cloudflare or security challenges (Turnstile CAPTCHA checks).
3. Session timeouts or throttling.

### The Solution: Min–Max Random Pacing
In ChatGPT Automator's settings, you can configure both **Minimum Delay** and **Maximum Delay** (in 0.5s intervals).

Before each subsequent prompt is sent, the extension calculates a random wait interval between your Min and Max values. This prevents rigid, robotic timing patterns.

---

## 2. Recommended Pacing Settings

| Workflow | Recommended Min Delay | Recommended Max Delay | Rationale |
|---|---|---|---|
| **Quick Text / Formatting** | `6.0s` | `12.0s` | Suitable for short sentences or formatting tasks. |
| **Long Form Content / Analysis** | `15.0s` | `30.0s` | Gives the browser time to clear memory and keeps request cadence natural. |
| **Image Generation (DALL-E)** | `35.0s` | `60.0s` | DALL-E has stricter generation cooldowns on ChatGPT web. |
| **Vision Analysis** | `15.0s` | `25.0s` | Allows image attachments to upload cleanly to ChatGPT servers before firing. |

---

## 3. Built-in Safety Features

### 3-Failure Auto-Stop
To protect your account and avoid burning through a 50-prompt queue while your session is broken:
- If **3 consecutive prompts fail** (e.g., due to a lost internet connection or an active CAPTCHA modal), the runner **stops automatically**.
- You can inspect the error, resolve the issue (e.g. solve a CAPTCHA or refresh the tab), and click **Retry Failed** to resume without losing completed work.

### Single-Tab Pinning
The extension binds to one specific ChatGPT tab. You can safely switch to other browser tabs or windows—prompts will never inadvertently send to a different tab or conversation.

### Graceful Abort
Clicking **Stop** immediately invokes ChatGPT's native `Stop Generating` button through an in-flight `AbortController`. This ensures orphan generation jobs do not continue in the background.

---

## 4. Best Practices Checklist

- [ ] **Start Small**: Test new batch files with 2–3 prompts before launching a 50-prompt batch.
- [ ] **Keep Tab Visible**: Keep the pinned ChatGPT tab in its own browser window (do not minimize or discard the tab).
- [ ] **Avoid Multiple Concurrent Queues**: Run only one queue at a time against your ChatGPT session.
- [ ] **Check Subscription Limits**: Be mindful of your account's plan tier (Free vs. ChatGPT Plus / Team) regarding model limits (e.g., GPT-4o usage limits).
