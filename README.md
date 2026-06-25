# Career Coach

A reference project for building a personal AI career coach that combines general career frameworks, role-specific knowledge, and user-owned context.

This repository is intentionally generic. It does not include private resumes, employer details, internal documents, conversation logs, or personal work history.

## What This Builds

The goal is a local-first career coaching assistant that can help with:

- Weekly career reviews
- Interview practice
- Resume and portfolio review
- Strategy document feedback
- Offer evaluation
- Role-specific learning plans

The key design idea is simple: a useful career coach is not just a chatbot over generic advice. It needs a structured context layer that explains the user's target role, operating environment, career goals, constraints, and preferred coaching style.

## Architecture

```text
career-coach/
├── README.md
├── SKILL.md or system-prompt.md
├── server.py or app/
├── context/
│   ├── profile.example.md
│   ├── domain-knowledge.md
│   └── coaching-principles.md
├── templates/
│   ├── weekly-review.md
│   ├── mock-interview.md
│   ├── resume-review.md
│   ├── strategy-review.md
│   └── offer-evaluation.md
└── docs/
    ├── BUILDING.md
    ├── REFERENCES.md
    └── ROADMAP.md
```

## Core Components

| Component | Purpose |
|---|---|
| `context/profile.example.md` | A sanitized profile schema users can copy and fill locally |
| `context/domain-knowledge.md` | Role, industry, market, or function-specific knowledge |
| `context/coaching-principles.md` | Rules for how the coach should diagnose, challenge, and recommend |
| `templates/` | Repeatable workflows for common career scenarios |
| `server.py` or `app/` | Optional UI/API layer for running the coach locally |

## Build Principles

1. Keep private context local unless the user explicitly chooses otherwise.
2. Separate generic framework content from personal profile content.
3. Make every workflow diagnostic before it becomes advisory.
4. Prefer one concrete next action over broad motivational advice.
5. Capture learning over time, but treat career logs as sensitive data.

## Quick Start

1. Copy `context/profile.example.md` to a private local file such as `context/profile.local.md`.
2. Fill in role, goals, constraints, target companies, and recurring challenges.
3. Choose one workflow from `templates/`.
4. Inject the profile, domain knowledge, coaching principles, and workflow template into your model prompt.
5. Save only sanitized learnings back into the public project.

## Privacy Boundary

Do not commit:

- Real resumes or compensation details
- Employer, manager, or teammate names
- Internal strategy docs
- Private work logs
- Interview feedback tied to identifiable companies
- API keys or model provider credentials

See [docs/BUILDING.md](docs/BUILDING.md) for the full design.

