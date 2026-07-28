## DealCortex — AI-Powered Deal Risk Intelligence Platform

**Eliminate pipeline misrepresentation with cross-source due diligence.** DealCortex reconstructs ground-truth deal health by joining Salesforce, Gmail, Gong, Slack, and LinkedIn in real time — surfacing the risk signals traditional CRM reporting hides.

### The Problem: Optimistic Reporting vs. Ground Truth

Sales teams often log subjective, overly favorable pipeline updates — the deal equivalent of an optimistic management narrative masking underlying fundamentals. The real risk signals live in fragmented, siloed data:

| Reported Status | Underlying Reality |
|---|---|
| "Deal is committed" | Counterparty stopped responding 12 days ago |
| "Forecast looks strong" | Call transcripts reveal unresolved objections |
| "Champion is aligned" | Key stakeholder changed roles last week |
| "Legal is on track" | Contract redlines stalled in email threads |
| "No blockers" | Internal channels show competitive/internal concern |

This mirrors a core due-diligence challenge: **surface-level reporting frequently diverges from underlying deal risk**, and that gap compounds when it isn't caught early.

### The Core Innovation: Cross-Source Due Diligence at Query Speed

DealCortex's differentiator is performing **cross-source SQL joins over heterogeneous enterprise data** — correlating CRM records with communications, call sentiment, and stakeholder-change signals in a single analytical pass, rather than manual cross-referencing across five disconnected tools.

### 4-Agent Risk Pipeline

1. **Routing Agent** — parses analyst intent, maps relevant data sources
2. **Query Agent** — converts intent into schema-safe, auditable SQL
3. **Risk Scoring Agent** — deterministic scoring engine producing Red/Amber/Green deal-health classification
4. **Insight & Execution Agent** — generates executive briefs, Slack-ready risk digests, and downloadable DOCX/PPTX deliverables for stakeholder review

### Why This Matters for Deal Teams

- **Due diligence, automated**: what would take an analyst hours of manual cross-checking across CRM, email, and call records happens in one query
- **Client-ready deliverables**: auto-generated executive briefs and presentation materials, formatted for immediate stakeholder use
- **Full auditability**: every generated SQL query and risk score is inspectable — no black-box scoring
- **Local-first privacy**: all data retrieval runs on-host, so sensitive deal data never leaves the environment

### Tech Stack
**Frontend:** React, Next.js, Tailwind CSS
**Backend:** Python, FastAPI, LLM-powered orchestration
**Data Layer:** Coral (cross-source query engine), PostgreSQL-compatible storage

