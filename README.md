# ChatGPT Automator Guide

[![License: MIT](https://img.shields.io/badge/License-MIT-purple.svg)](LICENSE)
[![Chrome Web Store](https://img.shields.io/badge/Chrome%20Web%20Store-ChatGPT%20Automator-blue.svg)](https://chrome.google.com/webstore)
[![Documentation](https://img.shields.io/badge/docs-guide-brightgreen.svg)](docs/)

Welcome to the official user manual, workflow recipes, and template cookbook for **ChatGPT Automator**.

ChatGPT Automator is a Manifest V3 Chrome extension that runs an automated sequential queue of prompts against the ChatGPT Web UI (`https://chatgpt.com/`) directly from a side panel beside your chat—without requiring OpenAI API keys or extra backend services.

---

## 📚 Documentation Index

| Guide | Description |
|---|---|
| [🚀 Installation & Setup](docs/01-installation-and-setup.md) | How to install from Chrome Web Store or load unpacked ZIP, open the side panel, and pin tabs. |
| [🎯 Prompt Modes & Features](docs/02-modes-and-features.md) | In-depth guide to Text, Text-to-Image, Image-to-Image, and Image-to-Text vision modes. |
| [📁 File Import & Dynamic Templating](docs/03-file-import-and-templating.md) | Formatting CSV, TXT, JSON, and MD batches; injecting `{{filename}}`, `{{basename}}`, and `{{index}}`. |
| [⏱️ Safe Pacing & Rate Limits](docs/04-safe-pacing-and-limits.md) | Natural pacing settings, anti-rate-limit tips, and the automatic 3-failure safety stop. |
| [❓ Troubleshooting & FAQ](docs/05-troubleshooting-and-faq.md) | Fixes for tab disconnects, page reload handling, stop vs. pause behavior, and export formatting. |

---

## ⚡ Recommended Pacing Quick Reference

Because ChatGPT Automator runs prompts through your interactive web session, pacing your requests with natural pauses keeps your session active and helps avoid temporary web cooldowns:

| Automation Workflow | Recommended Min Delay | Recommended Max Delay | Suggested Batch Size |
|---|---|---|---|
| **Short Text & Summaries** | `5s` | `12s` | 30 – 50 prompts |
| **Long Research & Code Generation** | `12s` | `25s` | 15 – 30 prompts |
| **Image Generation (DALL-E)** | `35s` | `60s` | 10 – 20 prompts |
| **Image-to-Image Transformations** | `40s` | `75s` | 10 – 15 prompts |
| **Vision Analysis (Image-to-Text)** | `15s` | `30s` | 20 – 40 prompts |

> [!TIP]
> Setting Min and Max delays to different values (e.g. Min: 8s, Max: 18s) gives you randomized pacing that mirrors organic human interaction.

---

## 📁 Ready-to-Use Templates

Explore the [`templates/`](templates/) folder for example batch files you can import directly into the extension:

- [`templates/blog-article-batch.csv`](templates/blog-article-batch.csv): CSV format with column headers for generating structured blog articles.
- [`templates/dalle-image-generation.txt`](templates/dalle-image-generation.txt): Plain-text prompt list for generating marketing visuals in 16:9 and 1:1 aspect ratios.
- [`templates/product-vision-analysis.csv`](templates/product-vision-analysis.csv): Image-to-text inspection prompt template using `{{filename}}` injection.

---

## 🤝 Community & Support

- **Found a bug or selector issue?** Submit an issue via our [Bug Report Template](.github/ISSUE_TEMPLATE/bug_report.md).
- **Want to share a prompt recipe?** Propose a template via [Pull Request](https://github.com/Jagaradoz/chatgpt-automator-guide/pulls) or open a [Template Request](.github/ISSUE_TEMPLATE/template_request.md).

---

## ⚖️ Disclaimer

*ChatGPT Automator is an independent tool and is not affiliated with, maintained by, or endorsed by OpenAI. Use responsibly and adhere to OpenAI's Terms of Use.*
