# 🎬 Movie Index Agentic Workflow with LlamaIndex

This project demonstrates how to use **LlamaIndex's AgentWorkflow** feature to build an **intelligent, multi-agent pipeline** for querying and summarizing movie data from a CSV dataset.

Each agent has a specific responsibility — from searching movie details to extracting budget and revenue, and finally summarizing the data for end users.

---
## 🧠 How It Works

It's a team of three agents using `FunctionAgent` from LlamaIndex:

             ┌─────────────┐
             │ User Prompt │
             └─────┬───────┘
                   ▼
            ┌──────────────┐
            │ SearchAgent  │  ← Looks up basic info
            └─────┬────────┘
                  ▼
        ┌────────────────────┐
        │ (if details found) │
        └────────┬───────────┘
                 ▼
         ┌──────────────┐
         │ BudgetRevenue│  ← Adds 💰 and 💸 data
         └─────┬────────┘
               ▼
         ┌──────────────┐
         │ SummaryAgent │  ← Final overview
         └──────────────┘



The agents **communicate and coordinate** using a shared `state` dictionary. If one agent is missing data, it can **trigger a handoff** to another.

---

## 🧱 Project Structure

| File | Description |
|------|-------------|
| `load_movie_agentworkflow.ipynb` | Full notebook with code, index creation, and agent setup |
| `data/movies.csv` | Sample movie dataset (title, genre, rating, etc.) |
| `README.md` | You’re here! Intro and guide |

---

## 🚀 Features

- ✅ Build a searchable index from a movie CSV
- 🤖 Use specialized agents for:
  - Description
  - Budget & revenue
  - Final summary
- 🔁 Smart agent handoff logic
- 📦 Powered by `LlamaIndex` and `OpenAI GPT`

---

## 🛠️ Setup Instructions

1. **Clone this repo**:
```bash
git clone https://github.com/your-user/movie-agentic-workflow.git
cd movie-agentic-workflow

pip install llama-index openai chardet nest_asyncio pandas


