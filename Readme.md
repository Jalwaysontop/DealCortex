# DealCortex

AI Deal Risk Intelligence, powered by Coral AI and a multi agent pipeline.

Ask a question in plain English. DealCortex cross references five data sources, scores every deal in your pipeline for risk, and generates shareable Slack digests, DOCX briefs, and PPTX decks, all in under 3 seconds.

Built at Pirates of Coral Bean Hackathon 2024.

## The Problem

Sales teams track deal health across five disconnected tools: Salesforce, Gmail, Gong, Slack, and LinkedIn. Nobody has time to manually cross reference all five before every forecast call, so risk signals get missed until a deal is already dead. DealCortex automates that cross referencing and turns it into a single conversational interface.

## Features

**AI Powered Risk Scoring**
A multi signal scoring engine analyzes email silence, call sentiment, champion changes, and more, then classifies deals as Red, Amber, or Green.

**Natural Language Queries**
Ask questions in plain English. The agent pipeline parses intent, selects the right data sources, and builds optimized SQL queries automatically.

**Slack Ready Digests**
Pipeline health reports formatted for Slack, prioritized by risk level with next steps your team can act on immediately.

**Pipeline Transparency**
Watch the agents work in real time. See which agents are running, what SQL was generated, and how each deal was scored.

**Auto Generated Docs and Slides**
Every query also produces an executive DOCX brief and a PowerPoint deck, surfaced directly in the output panel.

**Status Change Tracking**
When a deal's risk level shifts, DealCortex surfaces who and what triggered the change, instead of leaving you to dig through five tools to find out.

## How It Works

A 4 step AI pipeline runs end to end in under 3 seconds.

1. **Parse Intent** — Understand what's being asked: intent, timeframe, urgency.
2. **Select Sources** — Pick the right data sources from Salesforce, Gmail, Gong, Slack, and LinkedIn.
3. **Query and Score** — Generate Coral SQL, fetch the data, and score each deal for risk.
4. **Deliver Insights** — Return a dashboard with risk cards, narratives, and Slack digests.

## Data Sources

| Source | What it contributes |
|---|---|
| Salesforce | Pipeline stages, deal values, owners, close dates, CRM activity |
| Gmail | Email silence detection, thread length, legal flags, reply tracking |
| Gong | Call sentiment scores, objection counts, economic buyer attendance |
| Slack | Competitor mentions, escalation flags, internal team sentiment |
| LinkedIn | Champion job changes, hiring freezes, contact role tracking |

Coral SQL queries all five platforms through a single interface, so there are no point to point integrations to build or maintain.

## Tech Stack

**Frontend:** React, Next.js, Tailwind CSS
**Backend:** Python, FastAPI, LLM powered orchestration (CrewAI, Groq)
**Data Layer:** Coral (cross source query engine), PostgreSQL compatible storage

## Example Queries

- "Show me all deals at risk"
- "Which deals closing this month have gone silent?"
- "Forecast revenue for this quarter"
- "Deals where champion changed jobs"
- "Show objections from Gong calls"
- "Competitor mentions in Slack this week"

## What Broke (and what I fixed)

The individual signals were reliable on their own, but combined they contradicted each other. A deal could get flagged red for "email silence" when the conversation had simply moved to a new thread with a different contact. A champion change alert could fire because someone changed job titles internally, not companies, so the deal was fine but the system raised a false alarm anyway.

The fix was a reconciliation layer that checks signals against each other before scoring, instead of scoring them independently, plus a status change trail so that when a deal's risk level moves, the digest states specifically who and what triggered it. A tool that cries wolf gets ignored after two false alarms, so this reconciliation step ended up being the core engineering work, not the five API integrations.

## Getting Started

```bash
# clone the repo
git clone <repo-url>
cd dealcortex

# backend
cd backend
pip install -r requirements.txt
uvicorn main:app --reload

# frontend
cd frontend
npm install
npm run dev
```

Set the required environment variables (Coral API key, LLM provider key, and credentials for each connected data source) in a `.env` file before starting the backend.

## License

MIT
