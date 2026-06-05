# PROMPT INJECTION IN SLMs
**This project contains a research project aimed to check the robustness of SLMs against different type of prompt injections.**

**Evaluation of Adversarial Robustness and Safety Prompting in Small Language Models (SLMs)**

This repository contains the complete dataset engineering framework, experimental logs, and model evaluation pipeline for analyzing SLM vulnerabilities against prompt injection and lexical mutations.

## Live Environment
* **Executable Notebook:** https://www.kaggle.com/code/anaswaheed333333/nlp-proj
* **Research paper is also attached as NLP_Report**

## Dataset Architecture
The project evaluates models across a combined benchmark consisting of **1,190 unique test prompts**:
* **`Custom_QA_data.csv`**: 70 original, hand-crafted evaluation samples spread across 7 categories (Factual, Logic, Trick Questions, etc.).
* **`Baseline_QA.csv`**: 170 control pairs combining the curated suite with a 100-sample extraction from SQuAD v2.0.
* **`Adversarial_Robustness_Dataset.csv`**: 1,020 adversarial prompts generated via a Cartesian product of the baseline against 6 attack vectors (Prompt Injection, Negation, and Typo Noise).

## Evaluated Models
* `google/flan-t5-small`
* `google/flan-t5-base`
* `google/mt5-small`
* `distilgpt2`

## Experimental Results
The raw and aggregated metrics generated during the inference phase:
* `results.csv`: Complete row-by-row prediction and exact string match alignments.
  # Example of Result.csv
  <img width="784" height="268" alt="image" src="https://github.com/user-attachments/assets/eb29938a-68ee-401e-9911-e7ed8e0427b2" />

* `summary.csv`: Macro-averages for Accuracy, F1-Score, and Perplexity across all experimental settings.
* `ASR_by_attack.csv`: Vulnerability mapping showcasing Attack Success Rates (ASR) for each model by the injection type.
