# llm-agent-eda-system


🚀 Overview

Swaylytics is an Agentic AI system designed to perform autonomous exploratory data analysis (EDA) using a hybrid multi-agent architecture.

It combines a lightweight coding model with a powerful supervisory LLM to iteratively analyze data, generate insights, recover from errors, and produce publication-ready reports.


🧠 Key Idea

👉 Instead of just generating code, the system:

Understands data

Forms hypotheses

Writes & executes code

Recovers from errors

Iteratively improves analysis


analysis
🏗 System Architecture

The system follows a hybrid multi-agent architecture:

Coding Agent (DeepAnalyze-8B) → Generates Python code

Senior Analyst Agent (Gemini 3 Flash) → Planning, reasoning, error fixing

Validator Layer (AST-based) → Fixes common code issues

Execution Engine → Runs code in sandbox

Report Generator (Gemini 3.1 Pro) → Generates HTML reports


🔄 Core Workflow

Analyze → Code → Execute → Improve loop:

Analyze dataset & create plan

Generate Python code

Execute code in sandbox

Detect errors & fix automatically

Iterate until insights are complete

⚙️ Tech Stack

Frontend: Next.js

Backend: FastAPI

ML/LLM:

DeepAnalyze-8B

Gemini 3 Flash

Gemini 3.1 Pro

Execution: Python sandbox

Serving: vLLM

📊 Dataset & Evaluation

Evaluated on DS-1000 benchmark (1000 problems)

Covers libraries:

NumPy

Pandas

Matplotlib

Scikit-learn

TensorFlow


## 📂 Project Structure

```bash
swaylytics/
│
├── frontend/                 # Next.js frontend
│   ├── app/                  # Pages & routing
│   ├── components/           # UI components
│   └── lib/                  # API client & utilities
│
├── backend.py                # FastAPI entry point
│
├── backend_app/
│   ├── routers/              # API routes (chat, workspace, export)
│   └── services/             # Core logic (agent loop, execution, reporting)
│
├── requirements.txt          # Python dependencies
│
├── start.sh / start.bat      # Start frontend + backend
├── stop.sh / stop.bat        # Stop services
│
└── README.md
```
