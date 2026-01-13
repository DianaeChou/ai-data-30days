# ai-data-30days
30-day AI data engineering prep;
target:master in python and AI data analysis after 30-day learning;
week1: Python + Pandas（Day 1–7）;
week2: LLM 用于数据标注（Day 8–14）;
week3: SQL + 数据洞察（Day 15–21）;
week4：optimize CV and interview（Day 22–30）;

# AI-Powered Data Labeling & Insights Pipeline

A lightweight AI data engineering project that turns raw text feedback into structured labels and actionable insights using an LLM + a reproducible data pipeline.

## Table of Contents
- [Background](#background)
- [What This Project Does](#what-this-project-does)
- [Architecture](#architecture)
- [Data](#data)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [How to Run](#how-to-run)
- [Outputs](#outputs)
- [Quality & Evaluation](#quality--evaluation)
- [Cost & Performance Notes](#cost--performance-notes)
- [Limitations](#limitations)
- [Roadmap](#roadmap)

---

## Background
Manual labeling of user feedback is slow, inconsistent, and expensive. This project demonstrates how to embed an LLM into a data pipeline to:
- auto-label text (sentiment/topic/intent),
- enforce structured outputs,
- produce summary statistics and insights for decision-making.

## What This Project Does
Given a CSV of raw text feedback, the pipeline:
1. Ingests and cleans data (dedup, missing values, basic normalization)
2. Calls an LLM to generate structured labels in JSON format
3. Validates and retries failed/invalid outputs
4. Exports labeled data + analytics-ready tables
5. Generates an insights report (top issues, representative samples, trends)

## Architecture
**Flow:** `Raw CSV -> Cleaning -> LLM Labeling -> Validation/Retry -> Aggregation -> Report`

You can add a diagram here (recommended):
- `docs/architecture.png` or Mermaid diagram.

## Data
- **Input:** `data/raw/feedback.csv`
- **Required columns:** `id`, `text`
- **Example row:**
  - `id: 12345`
  - `text: "Battery drains too fast after the latest update."`

> Note: This repo includes only sample data. Full datasets are not committed.

## Tech Stack
- Python 3.10+
- pandas
- (Optional) SQLite for local SQL analytics
- LLM API (OpenAI / other providers)
- matplotlib (for simple charts)

## Getting Started

### Prerequisites
- Python 3.10+
- An LLM API key (see configuration below)

### Installation
```bash
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>
python -m venv .venv
# macOS/Linux
source .venv/bin/activate
# Windows
# .venv\Scripts\activate

pip install -r requirements.txt
