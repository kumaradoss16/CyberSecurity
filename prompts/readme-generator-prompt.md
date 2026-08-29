# README Generation Prompt

**Project:** Email Account & Digital Footprint Manager
**Purpose:** A ready-to-paste prompt that generates a professional, human-sounding `README.md` for this repository, following a fixed section structure.

---

## How to Use This

1. Fill in the four bracketed placeholders near the top of the prompt: `[INSERT GITHUB REPO URL]`, `[INSERT NAME / GITHUB USERNAME]`, `[INSERT LICENSE]`, `[INSERT NAME]` / `[INSERT GITHUB PROFILE / CONTACT]`.
2. Paste the whole prompt into a fresh AI conversation. For best results, attach or paste the real project files (or at least the module docstrings) alongside it, so the output is grounded in what's actually in the repo rather than guessed.
3. Re-run it (or just the affected sections) after finishing each new development phase — **Project Structure** and **Configuration** are the sections most likely to go stale as the project grows.

---

## The Prompt

````markdown
Act as a senior technical writer and developer documentation specialist
who has read this entire codebase and actually understands what it
does — not a generic README generator.

PROJECT CONTEXT:

Project name: Email Account & Digital Footprint Manager
GitHub repository: [INSERT GITHUB REPO URL]
Author: [INSERT NAME / GITHUB USERNAME]
License: [INSERT LICENSE, e.g. MIT]

What it does: A security-focused Python/FastAPI application that helps
an AUTHORIZED USER discover, organize, assess, secure, and clean up
online services associated with their own email address, using only
evidence they are authorized to access (their own inbox metadata via
OAuth, their own OAuth grant lists). It is explicitly NOT an
account-enumeration tool — it never probes login/signup/password-reset
flows on third-party sites.

Development approach: Built incrementally in 17 defined phases (see
the phase list below), each ending with a written Security Review
before moving to the next phase. Currently implemented: Phase 1
(project foundation) and Phase 2 (application authentication).

Tech stack actually in use so far:
- Backend: Python 3.12+, FastAPI, Pydantic v2, Pydantic-Settings
- Database: SQLAlchemy 2.0 (typed ORM), Alembic migrations, SQLite (dev), PostgreSQL (prod target)
- Auth/security: Argon2id password hashing (argon2-cffi), server-side
  sessions stored in the database, synchronizer-pattern CSRF tokens,
  a hand-rolled in-memory sliding-window rate limiter, structured
  logging with an automatic secret-redaction filter
- Testing: pytest, pytest-asyncio, httpx, FastAPI TestClient
- Planned but not yet built: Jinja2 + Bootstrap frontend, Gmail API,
  Microsoft Graph, Docker, Nginx, Redis/Celery

FULL PHASE ROADMAP (include this in the README's Roadmap section,
marking Phases 1-2 as done and the rest as planned):
1. Project foundation
2. Application authentication (register/login/logout, sessions, CSRF, rate limiting)
3. Account inventory + service registry + dashboard UI
4. Evidence model + evidence engine + confidence engine
5. Gmail OAuth + mailbox metadata scanning
6. Microsoft Graph integration
7. Service detection
8. OAuth inventory
9. Subscription detection
10. Cleanup center
11. Security hygiene dashboard
12. Reports
13. Data export/deletion
14. Docker
15. Ubuntu server deployment
16. Security testing
17. Production hardening

CURRENT PROJECT STRUCTURE (describe the purpose of every one of these
in the "Project Structure" section, in plain language, not just
restating the filename):

email_footprint_manager/
├── app/
│   ├── main.py              # FastAPI app factory, security-header middleware,
│   │                          restricted CORS, generic exception handlers, /health,
│   │                          mounts the auth router
│   ├── config.py            # Typed Settings object, loaded from .env — no
│   │                          hardcoded secrets anywhere in the codebase
│   ├── database.py          # SQLAlchemy engine/session/Base + get_db dependency
│   ├── logging_config.py    # Structured logging + a filter that auto-redacts
│   │                          anything password/token-shaped from logs
│   ├── exceptions.py        # AppError hierarchy — safe, generic client-facing
│   │                          error messages, no leaked stack traces
│   ├── security.py          # Argon2id password hashing, secure random token
│   │                          generation, constant-time comparison
│   ├── rate_limit.py        # Hand-rolled sliding-window rate limiter (documented
│   │                          single-process limitation; Redis planned later)
│   ├── utils.py             # Shared helpers (UTC time handling, etc.)
│   ├── models/
│   │   ├── user.py          # User ORM model (email, Argon2id hash, lockout fields)
│   │   └── session.py       # UserSession ORM model (server-side sessions + CSRF tokens)
│   ├── schemas/
│   │   └── auth.py          # Pydantic request/response models for registration,
│   │                          login, and the safe public user representation
│   ├── repositories/
│   │   ├── user_repository.py     # All User-table queries, in one auditable place
│   │   └── session_repository.py  # All session-table queries and expiry logic
│   ├── services/
│   │   └── auth_service.py  # Registration/login business logic: password
│   │                          verification, account lockout, timing-attack
│   │                          mitigation, session creation
│   └── api/
│       ├── deps.py          # FastAPI dependencies: get_current_session,
│       │                      get_current_user, require_csrf, cookie helpers
│       └── auth.py          # /auth/register, /auth/login, /auth/logout, /auth/me
├── migrations/               # Alembic migration environment and versions
├── tests/                     # pytest suite: test_health.py, test_security.py,
│                                test_rate_limit.py, test_auth.py, conftest.py
├── .env.example
├── requirements.txt
├── pyproject.toml
├── alembic.ini
├── SECURITY.md               # Living threat model + per-phase security reviews
└── README.md

TASK:

Write a complete, professional, and — this matters — GENUINELY HUMAN-
SOUNDING README.md for this repository. It should read like it was
written by the developer who actually built this and cares about it,
not like AI-generated boilerplate. Avoid generic filler phrases like
"This project aims to..." or "In today's digital world...". Be direct,
specific, and a little opinionated where it's warranted (e.g., explain
*why* certain security choices were made, not just that they exist).

Follow this exact section order and cover the following in each:

├── Project Title
    — The project name as an H1, plus a one-line tagline.

├── Short Description
    — 2-3 sentences: what it does, who it's for, and the one thing
      that makes it different (evidence-based, not enumeration-based).

├── Badges
    — Markdown badges for: Python version, license, build/test status
      (placeholder), and "Security-Focused" as a custom badge. Use
      shields.io syntax with [INSERT GITHUB REPO URL] wired in.

├── Overview
    — A few paragraphs on the problem this solves, the core workflow
      (DISCOVER → COLLECT EVIDENCE → IDENTIFY SERVICE → CLASSIFY
      CONFIDENCE → REVIEW → SECURE → CLEAN UP), and the explicit
      non-goals (never enumeration, never stores passwords).

├── Features
    — Bullet list of what's actually implemented right now (Phase 1 +
      2 features only — don't oversell unbuilt phases here; that's
      what Roadmap is for).

├── Technologies / Tech Stack
    — Organized by layer (Backend / Database / Security / Testing),
      pulled from the tech stack list above, with a one-line "why this
      one" note for the non-obvious choices (e.g., why Argon2id, why a
      hand-rolled rate limiter instead of a dependency).

├── Project Structure
    — The directory tree above, annotated, plus a short paragraph per
      top-level folder explaining its role in the architecture (why
      repositories/ is separate from services/, why api/ stays thin).

├── Prerequisites
    — Python 3.12+, pip, git; note SQLite needs nothing extra for dev,
      PostgreSQL is the production target.

├── Installation
    — Full working command sequence for BOTH Windows (PowerShell) and
      macOS/Linux: clone, venv, activate, pip install -r
      requirements.txt, copy .env.example to .env, alembic upgrade
      head, uvicorn app.main:app --reload. Use real, tested commands —
      not placeholders.

├── Usage
    — How to actually use the running API: hitting /health, and the
      full register → login → me → logout flow, including the CSRF
      header requirement on logout. Mention interactive docs at /docs.

├── Examples
    — Concrete curl examples for register/login/me/logout, showing
      real request/response JSON shapes (use example.com emails, never
      real-looking credentials).

├── Testing
    — How to run `pytest -v`, what's covered (health, security
      primitives, rate limiting, full auth flow including CSRF and
      account lockout), and that tests run against an isolated
      in-memory database, never real data.

├── Configuration
    — Table of every .env variable, its purpose, and its default —
      pulled from .env.example and config.py. Flag SECRET_KEY and
      DEBUG as security-relevant with a one-line warning on each
      (DEBUG=true bypasses the app's own safe error handler — explain
      this specifically, it's a real, non-obvious gotcha).

├── Documentation
    — Point to SECURITY.md for the full threat model and per-phase
      security reviews. Note that every module has an in-depth
      docstring (what/why/how/security notes/how-to-test) and that's
      the canonical source of truth for implementation details.

├── Roadmap
    — The 17-phase list above, phases 1-2 checked off, rest unchecked,
      as a markdown task list.

├── Contributing
    — Since this is currently a solo/learning project, say so plainly;
      note the phase-by-phase development discipline (don't skip
      ahead, security review at the end of each phase) as the
      contribution model if that changes later.

├── License
    — State [INSERT LICENSE] and link to a LICENSE file.

└── Author / Contact
    — [INSERT NAME], [INSERT GITHUB PROFILE / CONTACT].

OUTPUT FORMAT: Return only the final README.md content in valid
Markdown, ready to save directly as README.md. No preamble, no
explanation of what you're about to do — just the document.
````

---

## Notes

- The **Configuration** and **Project Structure** sections drift fastest — re-run this prompt (or just those sections) at the end of every new phase rather than letting the README go stale.
- Swap in real content, not placeholders, wherever you can — the more grounded the input, the less the output reads like generic AI filler.
- Want the actual `README.md` generated right now from this same prompt, using the real project already built? Just say so and it'll be written straight into the project folder.
