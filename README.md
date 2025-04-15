# 🎬 Movie Index Agentic Workflow with LlamaIndex

This project demonstrates how to use **LlamaIndex's AgentWorkflow** feature to build an **intelligent, multi-agent pipeline** for querying and summarizing movie data from a CSV dataset.

Each agent has a specific responsibility — from searching movie details to extracting budget and revenue, and finally summarizing the data for end users.

---

## 🧠 How It Works

Its a team of three agents using `FunctionAgent` from LlamaIndex:

          ┌─────────────┐
          │ User Prompt │
          └─────┬───────┘
                ▼
        ┌──────────────┐
        │ SearchAgent  │  ← Looks up basic info
        └─────┬────────┘
              ▼
   (if details found)
        ┌──────────────┐
        │ BudgetRevenue│  ← Adds 💰 and 💸 data
        └─────┬────────┘
              ▼
        ┌──────────────┐
        │ SummaryAgent │  ← Final overview
        └──────────────┘
