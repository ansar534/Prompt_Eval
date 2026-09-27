# Prompt Eval

Prompt Eval is a Python-based repository for evaluating prompt responses from multiple AI providers. It reads prompt text files, sends them through provider-specific models, and saves each generated answer as a PDF for review and comparison.

## Overview

This project is useful when you want to compare how different models respond to the same prompt set. The current implementation includes:

- Gemini model integration
- Groq model integration
- YAML-based configuration
- Prompt-folder organization by question
- PDF export of generated responses

## Project structure

```text
Prompt_Eval/
├── config/
│   ├── gemini_model_config.yaml
│   └── groq_model_config.yaml
├── src/
│   ├── main.py
│   ├── Prompts/
│   │   ├── Q1/
│   │   ├── Q2/
│   │   └── ...
│   └── core/
│       ├── geminiclient.py
│       └── groqclient.py
├── output/
│   ├── gemini/
│   └── groq/
├── requirements.txt
├── README.md
├── about.html
├── LICENSE
└── .gitignore
```

## Features

- Reads prompt files from structured folders such as Q1, Q2, Q3, etc.
- Uses LangChain and provider SDKs to invoke LLMs.
- Saves each output as a PDF using ReportLab.
- Supports multiple model providers through config-driven setup.
- Allows side-by-side comparison of model behavior and outputs.

## Requirements

Install the dependencies:

```bash
pip install -r requirements.txt
```

## Environment variables

Before running the app, create a `.env` file and add your API keys:

```bash
GEMINI_API_KEY=your_gemini_key
GROQ_API_KEY=your_groq_key
```

The project loads this file with Python-dotenv, so the credentials are available to the clients.

## Configuration

Model behavior and paths are configured in:

- `config/gemini_model_config.yaml`
- `config/groq_model_config.yaml`

These files define provider names, temperature, token limits, and prompt/output directories.

## Run the project

From the repository root:

```bash
python src/main.py
```

This runs both clients:

- Gemini processing
- Groq processing

The outputs are stored in the `output/` directory.

## About this repository

This project is designed for prompt evaluation and model comparison. It helps answer questions like:

- Which model gives better results for a given prompt?
- How does output quality differ between providers?
- How can generated reasoning or responses be archived for review?

See [about.html](about.html) for a browser-friendly project summary.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
