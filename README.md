# When Agentic LLMs Trust Poisoned Tools: Vulnerability of Clinical LLMs to Adversarial Guidelines

**Paper under review:** 
**Authors:** Alon Gorenshtein, Mahmud Omar, Yiftach Barash, Girish N Nadkarni, Eyal Klang.
Code developed by **Alon Gorenshtein**.

This work is associated with the **Bridge Gen AI Lab, BIDMC, Harvard Medical School**, and **Mount Sinai Medical Center, NY**.

---

Research harness to evaluate LLM trustworthiness in selecting between real and sham clinical guideline tools.

## Overview

This project provides a framework for testing whether Large Language Models (LLMs) can distinguish between authentic clinical guidelines and "sham" versions designed to test various vulnerabilities (e.g., outdated recommendations, prompt injections, fabricated citations).

## Key Components

- `src/`: Core logic, including the experiment runner and tool-calling flow.
- `scripts/`: Collection of scripts for running experiments, scoring results, and generating figures.
- `data/`: Sample clinical cases and guideline tools.

## Installation

1. Clone this repository.
2. Create a virtual environment:

   ```bash
   python -m venv venv
   source venv/bin/activate
   ```

3. Install dependencies:

   ```bash
   pip install -e .
   ```

## Configuration

1. Copy `.env.example` to `.env`:

   ```bash
   cp .env.example .env
   ```

2. Add your OpenAI API key to the `.env` file:

   ```env
   OPENAI_API_KEY=your_key_here
   ```

## Usage

### Running an Experiment

To run the main evaluation on the 100 cases:

```bash
python scripts/run_experiment.py --model gpt-4o --max-cases 10
```

### Scoring and Reporting

To generate a report from the experimental results:

```bash
python scripts/score_and_report.py --results-dir results/run_YYYYMMDD_HHMMSS
```

## Dataset

The primary datasets used in this study are located in the `data/` directory. The full dataset includes 500 clinical cases (`500cases_with_real_tools.json`, `500cases_final.json`, etc.) across multiple domains (Neurology, Infectious Disease, Critical Care, etc.) with paired authentic and sham guideline tools, enabling 10,500 total evaluations. We also provide a smaller `100cases_with_tools.json` file for quick testing.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
