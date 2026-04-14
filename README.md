# 📚 Textbook Summarizer

![Python 3.11+](https://img.shields.io/badge/Python-3.11+-blue?style=flat-square&logo=python&logoColor=white)
![MIT License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)
![Gemma 4](https://img.shields.io/badge/Gemma_4-LLM-orange?style=flat-square&logo=google&logoColor=white)
![Privacy-First](https://img.shields.io/badge/Privacy-100%25_Local-brightgreen?style=flat-square)
![Ollama](https://img.shields.io/badge/Ollama-Inference-blueviolet?style=flat-square)

> Turn dense textbook chapters into structured summaries, glossaries, concept maps, and quizzes — all locally with Gemma 4.

## Architecture

```
┌──────────────────────────────────────────────┐
│            Textbook Input (.txt)              │
│                    │                          │
│            ┌──────▼───────┐                  │
│            │   Chapter    │                  │
│            │   Splitter   │                  │
│            └──────┬───────┘                  │
│                   │                          │
│            ┌──────▼───────┐                  │
│            │   Ollama     │                  │
│            │  (Gemma 4)   │                  │
│            └──────┬───────┘                  │
│     ┌─────────────┼─────────────┐            │
│ ┌───▽────┐  ┌─────▽────┐  ┌────▽─────┐     │
│ │Summary │  │ Glossary │  │ Concept  │     │
│ │        │  │          │  │   Map    │     │
│ └────────┘  └──────────┘  └──────────┘     │
│                   │                          │
│            ┌──────▽───────┐                  │
│            │  Study Quiz  │                  │
│            │  Generator   │                  │
│            └──────────────┘                  │
└──────────────────────────────────────────────┘
```

## Features

1. **Chapter Summarization** — Generates structured summaries with key concepts, definitions, and review questions
2. **Multiple Summary Styles** — Choose from concise bullet-points, detailed paragraphs, or study-guide format
3. **Glossary Generation** — Automatically extracts and defines technical terms from the chapter text
4. **Concept Map Creation** — Builds relationship maps between key topics for visual learning
5. **Quiz Generation** — Creates study questions with factual recall and critical thinking prompts
6. **Formula Extraction** — Identifies and explains equations, formulas, and their variables
7. **Rich CLI Interface** — Beautiful terminal output with color-coded sections and progress bars
8. **Streamlit Web UI** — Browser-based interface for uploading textbooks and browsing summaries
9. **FastAPI REST Endpoint** — Programmatic access for batch summarization workflows
10. **100% Local & Private** — All inference runs through Ollama locally; your study materials stay on your machine

## Quick Start

### Prerequisites

- Python 3.11 or higher
- [Ollama](https://ollama.com/) installed and running
- Gemma 4 model pulled: `ollama pull gemma4`

### Installation

```bash
git clone https://github.com/kennedyraju55/textbook-summarizer.git
cd textbook-summarizer
pip install -r requirements.txt
```

### Running the Application

**CLI:**
```bash
python -m src.textbook_summarizer.cli summarize --file chapter.txt --style concise
```

**Web UI:**
```bash
streamlit run src/textbook_summarizer/web_ui.py
```

**Docker:**
```bash
docker-compose up
```

## Tech Stack

| Technology | Purpose |
|-----------|---------|
| Gemma 4 + Ollama | Local LLM inference for summarization and quiz generation |
| Click + Rich | CLI framework with formatted terminal output |
| Streamlit | Interactive web dashboard for textbook uploads |

## Project Structure

- `src/textbook_summarizer/` — Core application: chapter splitting, summarization, glossary, quiz, CLI, web UI
- `common/` — Shared LLM client utilities for Ollama integration
- `tests/` — Unit and integration test suite
- `docs/` — Documentation and architecture diagrams
- `examples/` — Sample textbook chapters and generated summaries

## Author

**Nrk Raju Guthikonda** — [GitHub: kennedyraju55](https://github.com/kennedyraju55) · [Dev.to](https://dev.to/kennedyraju55) · [LinkedIn](https://www.linkedin.com/in/nrk-raju-guthikonda-504066a8/)
