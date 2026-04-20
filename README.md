# LLM-Assisted Thematic Analysis

A Jupyter notebook for performing reflexive thematic analysis (Braun & Clarke) on interview transcripts using a local, open-source language model. Your data never leaves your computer.

---

## What it does

Analyzes `.docx` interview transcripts and produces a structured list of themes, each with a description and supporting quotes from the participant. Because open-source models have a limited context window, long transcripts are automatically split into chunks and analyzed in stages before being consolidated into a final report.

---

## Requirements

- Python 3.8 or higher
- [Ollama](https://ollama.com) installed and running
- A model pulled via Ollama (recommended: `qwen2.5:7b`)

```bash
ollama pull qwen2.5:7b
```

---

## Setup

1. Clone or download this repository
2. Open `thematic_analysis.ipynb` in Jupyter or Google Colab
3. Run Step 1 to install dependencies
4. Edit Step 2 with your folder paths and model name
5. Run all remaining cells

---

## Transcript format

Transcripts should be saved as `.docx` files. Interviewer turns are automatically removed — the pipeline recognizes labels like `Interviewer:`, `Researcher:`, `Q:`, and `Moderator:`. If your transcripts use a different label, see the note in Step 4 of the notebook.

---

## Output

Each transcript produces a `<filename>_themes.txt` file containing:

- A structured theme list with descriptions and participant quotes
- Chunk-level notes at the bottom for auditing and traceability

A `run_log.json` is also saved to track which files have been processed.

---

## Privacy

This pipeline runs entirely locally using Ollama. No transcript data is sent to any external server or API.
