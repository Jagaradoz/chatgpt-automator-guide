# 📁 File Import & Dynamic Templating

ChatGPT Automator allows you to batch import prompts from structured files and inject dynamic metadata directly into your prompts.

---

## 1. Supported Import Formats

You can drag and drop or use the file picker to import prompts from:

### CSV (`.csv`)
- Standard RFC-4180 compliant CSV files.
- If your CSV includes headers, the importer will auto-detect columns like `prompt`, `input`, `query`, or `content`.
- If no header is present, the first column is used as the prompt text.
- Escaped quotes and multi-line fields enclosed in quotes are supported.

```csv
prompt,topic
"Explain quantum entanglement for a 10-year old",Physics
"Summarize the French Revolution in 3 bullet points",History
```

### Plain Text (`.txt`)
- Each non-empty line is treated as an individual prompt in the queue.
- Great for quick lists or generated prompt collections.

### JSON (`.json`)
- Accepts an array of strings:
  ```json
  [
    "Write a haiku about autumn",
    "Write a limerick about programming"
  ]
  ```
- Or an array of objects with a `prompt` key:
  ```json
  [
    { "prompt": "Analyze market trends in electric vehicles" },
    { "prompt": "Draft an executive summary for Q3 earnings" }
  ]
  ```

### Markdown (`.md`)
- Extracts each blockquote or list item as individual prompt tasks.

---

## 2. Dynamic Templating Variables

When crafting prompts—especially in image-pairing or batch file workflows—you can use special handlebars-style tags that resolve dynamically at runtime:

| Variable | Description | Example Output |
|---|---|---|
| `{{filename}}` | The full name of the attached file (including extension). | `diagram_v2.png` |
| `{{basename}}` | The name of the file without extension. | `diagram_v2` |
| `{{index}}` | The 1-based sequential index of the prompt in the queue. | `1`, `2`, `3` ... |

### Example Prompt using Variables:
```text
Inspect the attached image {{filename}}. 
Provide an SEO-friendly title and alt-text for image #{{index}}.
Use the filename "{{basename}}" as the slug reference.
```

---

## 3. Exporting Completed Runs

Once a run completes, you can export your captured results:
- **JSON**: Full structured export with prompt text, response markdown, timestamp, duration, and status.
- **CSV**: Spreadsheet-ready format compatible with Google Sheets, Excel, and Notion databases.
- **Markdown (`.md`)**: A consolidated markdown document with headings for each prompt and formatted response blocks.
- **Direct Downloads**: If configured, each generated response or DALL-E image is saved straight into your `Downloads/` directory automatically.
