# 🎯 Prompt Modes & Features

ChatGPT Automator supports four specialized execution modes to streamline different AI workflows.

---

## 1. The Four Execution Modes

### Mode 1: Text (`text`)
- **Use case**: Standard batch queries, question answering, article generation, data extraction, translation, or code rewriting.
- **How it works**: Injects the prompt sequentially into ChatGPT's ProseMirror editor, submits the message, and streams the markdown response back into the panel's queue table.

### Mode 2: Text-to-Image (`text-to-image`)
- **Use case**: Generating multiple artwork, concept designs, or UI mockups using ChatGPT's integrated DALL-E engine.
- **Aspect Ratios**: You can select presets such as `1:1` (Square), `16:9` (Widescreen landscape), `9:16` (Story/Mobile portrait), `4:3`, or `3:4`.
- **Auto-Download**: When enabled in settings, the generated image is downloaded directly to your Chrome `Downloads/` directory as soon as ChatGPT finishes rendering it.

### Mode 3: Image-to-Image (`image-to-image`)
- **Use case**: Iterative image modifications, style transfers, character consistency, or applying variations to existing images.
- **How it works**: Attaches source images, applies your modification prompt, and awaits the rendered image output.

### Mode 4: Image-to-Text (`image-to-text`)
- **Use case**: Vision analysis, OCR extraction, product photo categorization, accessibility alt-text generation, and diagram explanation.
- **How it works**: Uploads your source images and submits your vision instructions (e.g., *"Extract all table data from this invoice screenshot as JSON"*).

---

## 2. Image Pairing Modes

When working with both prompts and image attachments, you can choose how they pair:

### Sequential (1-to-1)
- Prompt #1 is paired with Image #1.
- Prompt #2 is paired with Image #2.
- **Example**: A list of 10 different product photos, each paired with an individual product-specific question.

### Broadcast (Cartesian)
- Every prompt is executed against **every** attached image.
- **Example**: You upload 5 photos and specify 2 prompts (*"Describe the lighting"* and *"Identify the dominant color palette"*). The queue will execute $5 \times 2 = 10$ total jobs.

---

## 3. Queue Controls & Life-Cycle

- **Start**: Initiates execution from the first pending job in the queue.
- **Pause**: Instructs the runner to gracefully finish the currently active prompt and stop before starting the next one.
- **Stop**: Halts execution immediately and aborts any in-flight response generation in the ChatGPT tab.
- **Retry / Retry Failed**: Retries a single failed job or all failed jobs in one click.
- **Session Persistence**: If you accidentally close the side panel or browser window, your queue progress, completed responses, and inputs are preserved in extension storage.

---

## Next Steps
- Learn how to import batches using CSV, TXT, or JSON in [File Import & Dynamic Templating](03-file-import-and-templating.md).
