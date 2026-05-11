# Beyond the Answer: Financial Reasoning with FinQA and Qwen2.5

This project explores numerical and symbolic reasoning capabilities of small language models on the FinQA benchmark using **Qwen2.5-0.5B-Instruct**.

The objective was not to maximize benchmark accuracy, but to analyze how and why small LLMs fail on structured financial reasoning tasks involving:

* financial tables
* earnings reports
* symbolic arithmetic programs

---

## Project Overview

The project was completed as part of the **LLM for Finance RA Coding Assignment**. 

The assignment consisted of:

### Layer 1 — Read & Understand

* Dataset exploration
* Program structure analysis
* Evidence distribution analysis
* Execution vs program accuracy understanding

### Layer 2 — Plan & Build

* Qwen2.5-0.5B reasoning pipeline
* Execution evaluation on 100 examples
* Error taxonomy
* Context sensitivity experiments

### Layer 3 — Open Extension

* Symbolic verification
* Reasoning reliability analysis
* Retrieval and parsing improvements

---

# Dataset

Dataset: **FinQA**

Contains:

* 8,281 financial QA examples
* mixed table + text reasoning
* symbolic programs
* numerical answers

Example reasoning chain:

```text
subtract(5829,5735)
divide(#0,5735)
```

---

# Model Used

* Qwen2.5-0.5B-Instruct
* HuggingFace Transformers
* Google Colab T4 GPU

---

# Pipeline

```text
FinQA Input
    ↓
Prompt Builder
    ↓
Qwen2.5-0.5B-Instruct
    ↓
Program Parser
    ↓
Execution Engine
    ↓
Evaluation
```

---

# Key Findings

## Reasoning Depth

Most FinQA questions involve:

* 1-step reasoning
* 2-step reasoning

---

## Evidence Sources

Questions rely heavily on:

* financial tables
* structured numerical retrieval

Removing tables degraded performance more than removing text.

---

## Error Taxonomy

Main failure modes:

* Parsing Error
* Retrieval Error
* Operation Error

The dominant issue was:

> the model generated natural language explanations instead of executable symbolic programs.

---

## Important Insight

A model can produce:

* correct numerical answers
* incorrect reasoning programs

This is important for financial reliability because correct outputs do not guarantee trustworthy reasoning.

---

# Layer 3 Extension

Implemented:

* symbolic verification
* program execution validation
* parser consistency checks

Explored improvements:

* retrieval re-ranking
* constrained decoding
* symbolic-neural hybrid reasoning

---

# Results

The experiments demonstrated that:

* small instruction-tuned LLMs struggle with symbolic financial reasoning
* retrieval quality is critical
* structured program generation is difficult without fine-tuning
* symbolic verification improves reliability

---

# Tech Stack

* Python
* PyTorch
* Transformers
* Pandas
* Matplotlib
* Google Colab

---

# Repository Structure

```text
├── Code_Submission.ipynb
├── README.md
├── report.pdf
├── presentation.pptx
├── finqa_results.csv
└── outputs/
```

---

# Running the Notebook

Install dependencies:

```python
!pip install transformers accelerate bitsandbytes pandas matplotlib seaborn tqdm
```

Run:

* dataset analysis
* Qwen inference
* evaluation
* error analysis
* visualization cells

---

# Future Work

Possible future improvements:

* fine-tuning on FinQA
* constrained decoding
* better retrieval ranking
* tool-augmented reasoning
* symbolic planners

---

# Author

Aayush Choudhary
IIIT Delhi
