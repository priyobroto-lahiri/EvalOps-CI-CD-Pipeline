# EvalOps CI/CD Pipeline

A production-grade automated evaluation pipeline that integrates LLM quality benchmarks directly into the software development lifecycle (SDLC) via GitHub Actions.

## 🎯 The Problem
Prompt engineering is fragile. A small change in a system prompt or a model update can silently degrade performance (regression). Manual testing before every deployment is impossible. This project builds a "Quality Gate" that automatically tests every prompt change and blocks deployments if quality thresholds are not met.

## 🛠️ The Approach
This pipeline transforms evaluation from a manual task into a continuous process:

1.  **Automated Regression Testing:** Every commit triggers a suite of 25+ test cases using **Promptfoo**.
2.  **Go/No-Go Deployment Gates:** Deployment to production is automatically blocked if metrics (e.g., Faithfulness, Semantic Similarity) drop below a pre-defined threshold (e.g., 0.85).
3.  **Agent Trajectory Evaluation:** Specialized evaluation for Agentic workflows (LangGraph), ensuring the AI follows the correct tool-calling sequence.
4.  **Version-Controlled Prompts:** Managing prompts as code, with clear history and "Side-by-Side" (A/B) comparison reports.

## 🚦 Pipeline Status (Preview)
| Metric | Threshold | Current | Status |
| :--- | :--- | :--- | :--- |
| **Faithfulness** | > 0.85 | TBD | ⚪ Pending |
| **Answer Relevancy**| > 0.80 | TBD | ⚪ Pending |
| **Agent Trajectory** | 100% | TBD | ⚪ Pending |

## 🚀 Tech Stack
- **CI/CD:** GitHub Actions
- **Eval Tools:** Promptfoo, LangGraph (Agentic)
- **Reporting:** Markdown-based deployment summaries
- **Logic:** YAML, Python
