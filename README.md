<div align="center">
<img src="https://img.shields.io/badge/📖_Textbook_Summarizer-Local_LLM_Powered-blue?style=for-the-badge&labelColor=1a1a2e&color=16213e" alt="Project Banner" width="600"/>

<br/>

<img src="https://img.shields.io/badge/Gemma_4-Ollama-orange?style=flat-square&logo=google&logoColor=white" alt="Gemma 4"/>
<img src="https://img.shields.io/badge/Python-3.9+-blue?style=flat-square&logo=python&logoColor=white" alt="Python"/>
<img src="https://img.shields.io/badge/Streamlit-Web_UI-red?style=flat-square&logo=streamlit&logoColor=white" alt="Streamlit"/>
<img src="https://img.shields.io/badge/Click-CLI-green?style=flat-square&logo=gnu-bash&logoColor=white" alt="Click CLI"/>
<img src="https://img.shields.io/badge/License-MIT-yellow?style=flat-square" alt="License"/>

<br/><br/>

<strong>Part of <a href="https://github.com/kennedyraju55/90-local-llm-projects">90 Local LLM Projects</a> collection</strong>

</div>

<br/>
# 📚 Textbook Summarizer

![Python](https://img.shields.io/badge/python-3.10%2B-blue)
![LLM](https://img.shields.io/badge/LLM-Ollama%2FGemma4-green)
![CLI](https://img.shields.io/badge/CLI-Click-orange)
![Web](https://img.shields.io/badge/Web-Streamlit-red)
![Tests](https://img.shields.io/badge/tests-pytest-yellow)

AI-powered textbook summarizer with multi-chapter processing, concept map generation, key terms glossary, and study question generation. Supports three summary styles and both CLI and Streamlit web interfaces.

## Features

- **Multi-Chapter Processing** — Automatically detects and processes multiple chapters
- **Concept Map Generation** — Visual concept relationships in text format
- **Key Terms Glossary** — Auto-extracted definitions and terminology
- **Study Questions** — Generated quiz questions with answers (configurable count)
- **Three Summary Styles** — Concise bullets, detailed explanations, or study-guide Q&A
- **Streamlit Web UI** — Upload chapters, adjust depth, view concepts and quizzes
- **Chapter Detection** — Recognizes Chapter, Unit, Lesson heading formats
- **YAML Configuration** — Customizable via `config.yaml`

## Installation

```bash
cd 17-textbook-summarizer
pip install -r requirements.txt
ollama serve && ollama pull gemma4
```

## Usage

### CLI

```bash
# Concise summary (default)
python -m src.textbook_summarizer.cli --file chapter.txt

# Detailed summary
python -m src.textbook_summarizer.cli --file chapter.txt --style detailed

# Multi-chapter processing with all study aids
python -m src.textbook_summarizer.cli --file textbook.txt --multi-chapter --glossary --concept-map --quiz

# Custom quiz question count
python -m src.textbook_summarizer.cli --file chapter.txt --quiz --num-questions 10
```

### Web UI

```bash
streamlit run src/textbook_summarizer/web_ui.py
```

### CLI Options

| Option              | Required | Default    | Description                          |
|---------------------|----------|------------|--------------------------------------|
| `--file`            | Yes      | —          | Path to textbook chapter text file   |
| `--style`           | No       | `concise`  | concise / detailed / study-guide     |
| `--multi-chapter`   | No       | —          | Process as multi-chapter file        |
| `--glossary`        | No       | —          | Generate key terms glossary          |
| `--concept-map`     | No       | —          | Generate concept map                 |
| `--quiz`            | No       | —          | Generate study questions             |
| `--num-questions`   | No       | `5`        | Number of quiz questions             |
| `--config`          | No       | —          | Path to config.yaml                  |
| `--verbose`         | No       | —          | Enable debug logging                 |

## Testing

```bash
python -m pytest tests/ -v
```

## Project Structure

```
17-textbook-summarizer/
├── src/textbook_summarizer/
│   ├── __init__.py
│   ├── core.py              # Summarization logic
│   ├── cli.py               # Click CLI interface
│   ├── web_ui.py            # Streamlit web interface
│   ├── config.py            # Configuration management
│   └── utils.py             # Helpers (chapter splitting, word count)
├── tests/
│   ├── __init__.py
│   ├── test_core.py
│   └── test_cli.py
├── config.yaml
├── setup.py
├── requirements.txt
├── Makefile
├── .env.example
└── README.md
```

## 📸 Screenshots

<div align="center">
<table>
<tr>
<td><img src="https://via.placeholder.com/400x250/1a1a2e/e94560?text=CLI+Interface" alt="CLI Interface"/></td>
<td><img src="https://via.placeholder.com/400x250/16213e/e94560?text=Web+UI" alt="Web UI"/></td>
</tr>
<tr>
<td align="center"><em>CLI Interface</em></td>
<td align="center"><em>Streamlit Web UI</em></td>
</tr>
</table>
</div>
