# AI Job Search & Application Agent

AI-assisted job discovery, matching, application preparation, approval, tracking, and reporting system.

## Vision

Build a reliable Telegram-first assistant that helps a job seeker discover relevant recent roles, evaluate fit against a resume and preferences, prepare application materials, request human approval before consequential actions, track applications, and send daily reports.

## Core Principles

- Human-in-the-loop for consequential actions
- Deterministic filtering before AI evaluation
- Provider-agnostic LLM architecture
- Gemini as the primary LLM, with Groq and OpenRouter fallbacks
- Official/public job sources and permitted APIs only
- Persistent tracking and auditability
- Privacy by design
- Portfolio-quality documentation and implementation

## Proposed Architecture

```text
Telegram
   |
   v
 Make (orchestration)
   |
   +-------------------+--------------------+
   |                   |                    |
   v                   v                    v
Job Sources       AI Gateway             Supabase
APIs / feeds      |                     DB / tracking
                  +-- Gemini
                  +-- Groq
                  +-- OpenRouter
   |
   v
Human Approval via Telegram
   |
   v
Application preparation / permitted submission
   |
   v
Tracking + daily report
```

## Technology Roles

| Technology | Role |
|---|---|
| Telegram Bot | Commands, approvals, notifications, daily reports |
| Make | Cloud workflow orchestration |
| Gemini Flash | Primary LLM |
| Groq | Primary fallback LLM |
| OpenRouter | Secondary fallback/model gateway |
| Supabase | Database, state, tracking, audit data |
| GitHub | Code, documentation, version control |

## Scope

### Candidate profile
- Resume/profile
- Target roles
- Preferred countries/cities
- Work-mode preferences
- Salary preferences
- Relocation/visa preferences
- Skills and experience

### Job discovery
- Recent job discovery
- Source normalization
- Duplicate detection
- Deterministic filters
- Job metadata extraction

### AI matching
- Resume-to-job fit scoring
- Match explanation
- Missing-skill identification
- Application priority

### Application preparation
- Tailored cover letter
- Application-answer drafts
- Resume tailoring recommendations
- Telegram approval workflow

### Tracking and reporting
- Saved jobs
- Applications and statuses
- Follow-up dates
- Daily Telegram report
- Errors and AI-provider failover events

## Important Boundary

The agent will not blindly automate applications across arbitrary websites. Automatic submission is considered only where an official, permitted application mechanism exists and the required authorization is available. Otherwise, the agent prepares the application and provides the official application link for the user.

## Roadmap

- [ ] Phase 0 — Product definition and architecture
- [ ] Phase 1 — Candidate profile and requirements
- [ ] Phase 2 — Job discovery and normalization
- [ ] Phase 3 — AI matching engine
- [ ] Phase 4 — Telegram agent and human approval
- [ ] Phase 5 — Supabase persistence and tracking
- [ ] Phase 6 — Application preparation
- [ ] Phase 7 — LLM failover and reliability
- [ ] Phase 8 — Daily reporting and observability
- [ ] Phase 9 — Security and auditability
- [ ] Phase 10 — Portfolio demo and productization assessment

## Repository Structure

```text
.
├── README.md
├── docs/
│   ├── 01-product/
│   ├── 02-requirements/
│   ├── 03-process/
│   ├── 04-architecture/
│   ├── 05-data-model/
│   ├── 06-ai/
│   ├── 07-automation/
│   ├── 08-security/
│   └── 09-testing/
├── workflows/
│   └── make/
├── supabase/
├── prompts/
├── examples/
└── tests/
```

## Security

Never commit API keys, bot tokens, Supabase service-role keys, OAuth tokens, private resumes, or application credentials. Runtime secrets must be stored in environment variables or platform-managed secret storage.

## Portfolio Value

This project demonstrates business analysis, process design, workflow automation, AI-assisted decision support, human-in-the-loop design, LLM provider failover, data modeling, API integration, security, auditability, and product thinking.