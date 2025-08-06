# FinRobot: Financial AI Agents

This repository contains two notebooks built on top of **FinRobot**, an open-source multi-agent framework for automating financial analysis and equity research using LLMs.

---

## 📘 Notebooks Overview

### 1. `agent_rag_qa.ipynb` — AI Analyst for 10-K Q&A
This notebook creates a **Retrieval-Augmented Generation (RAG)** agent capable of answering financial questions from 10-K filings of a given company.

### 2. `agent_annual_report.ipynb` — AI Assistant to Write an Annual Report
This notebook generates a full **PDF annual report** from a 10-K form by coordinating tools and analysis steps via a FinRobot assistant.

---

## ⚙️ Setup Instructions

1. Clone the repository:
   ```bash
   git clone https://github.com/nayanaiyer/Fin-LLM.git
   cd FinRobot
   ```

2. Install dependencies
    ```bash
    pip install -r requirements.txt
    pip install -e .
    ```
