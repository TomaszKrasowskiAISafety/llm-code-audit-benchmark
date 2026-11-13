# LLM Code-Audit Robustness Benchmark

An open-source evaluation harness designed to measure the adversarial robustness and defensive code-auditing capabilities of frontier Large Language Models (LLMs) in multi-turn agentic workflows.

## Research Overview

As LLMs are increasingly integrated into automated security pipelines and static code analysis workflows, understanding their alignment boundaries under indirect prompt injection becomes critical. This repository hosts the evaluation scripts and test cases used to benchmark:

1. **Defensive Vulnerability Detection:** Evaluating model accuracy and false-positive rates on obfuscated or ambiguous open-source code snippets (Python, C/C++, JavaScript).
2. **Indirect Prompt Injection Resilience:** Testing whether multi-step adversarial instructions hidden within code comments, docstrings, or dependency files can subvert system-prompt safety boundaries.
3. **Defensive System-Prompt Mitigation:** Comparing prompt-hardening strategies across different model architectures and context lengths.

## Repository Structure

* `evaluate_prompt.py` – Core evaluation harness for running reproducible test cases against LLM APIs with automated retry logic.
* `samples/` – Controlled, sandboxed code snippets containing benign logic, known vulnerability patterns (CWE), and embedded comment-based injection probes *(in development)*.

## Usage

1. Install dependencies:
   ```bash
   pip install anthropic
   ```
2. Set your API key:
   ```bash
   export ANTHROPIC_API_KEY="your-api-key-here"
   ```
3. Run the evaluation harness:
   ```bash
   python evaluate_prompt.py
   ```

## Responsible Disclosure & Ethics

All experiments are conducted strictly in isolated, sandboxed environments using synthetic or publicly disclosed open-source vulnerability patterns. No live systems are targeted.
