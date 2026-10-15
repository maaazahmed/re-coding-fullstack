# Re-Coding Fullstack: Roadmap (Oct 2026 – Jan 2027)

> **Goal:** rebuild your ability to write fullstack code **from your own head**, then use AI as a tool, not a crutch.
> **Languages:** JavaScript · TypeScript · Python
> **Stack:** React · Node.js/Express · Python/FastAPI · MongoDB + PostgreSQL · Docker · Git
> **Time:** ~2 hours a day for the main (JS/TS) plan + **3 × 45 min per week** for the 🐍 Python track

## Folder structure

```
re-coding-fullstack/
├── README.md                      ← you are here (overview, rules, score tracker)
├── 2026-10-October/
│   ├── Week-01_Oct-15-to-Oct-18/
│   │   ├── plan.md                ← day-by-day tasks
│   │   ├── quiz.md                ← this week's quiz (answers hidden)
│   │   └── interview-prep.md      ← this week's interview tasks
│   └── ...
├── 2026-11-November/
├── 2026-12-December/
└── 2027-01-January/
```

Every file has a **🐍 Python track** section near the end with that week's Python sessions, Python quiz questions and Python interview tasks.

**Each week:** open `plan.md` on Monday → do the tasks → take `quiz.md` on Sunday → do `interview-prep.md` across the week.

---

## The rules (read them every Monday)

1. **Write first:** try every problem for **20–30 minutes** before you ask for any help.
2. **Ask AI for hints only:** "Give me a hint, not the code" or "Review my code and tell me what's wrong, don't fix it."
3. **Don't paste code you can't explain.** If you can't explain it line by line, delete it and rewrite it.
4. **Commit daily** to GitHub. Your green squares are your proof.
5. **Log every day** in the log table at the bottom of each week's `plan.md`.

### How to use AI by phase

| Phase | AI usage allowed |
|---|---|
| Weeks 1–6 | Explanations and concepts only. **No code generation.** |
| Weeks 7–12 | Hints, code review, explaining errors. You write all the code. |
| Weeks 13–16 | Full pair programming, but you must be able to explain every line. |

### Daily routine (about 2 hours)
| Time | Activity |
|---|---|
| 15 min | Review yesterday's notes and answer a few questions from this week's `quiz.md` |
| 30 min | 1 coding problem (Codewars/LeetCode easy, no AI) |
| 60 min | The main task for the day in `plan.md` |
| 15 min | Write in your log: what you did, where you got stuck, what you learned |

---

## Overview

| Month | Weeks | Focus | Output |
|---|---|---|---|
| **October** | 1–3 | JS fundamentals, Git, DOM | 3 vanilla JS mini-apps |
| **November** | 4–7 | TypeScript, React, Node/Express, REST | Todo app (React) and Notes REST API |
| **December** | 8–12 | Databases, authentication, fullstack integration, testing | **Project 1:** Expense Tracker (fullstack) |
| **January** | 13–16 | Next.js, deployment, system design, interviews | **Project 2:** Portfolio-grade app + interview ready |

### 🐍 Python track overview

The Python track runs in parallel and mirrors the JS/TS topics, so you learn each concept in both languages.

| Weeks | Python focus | Output |
|---|---|---|
| 1–3 | Core types, comprehensions, functions, decorators, errors, modules, files | CLI todo app (`argparse` + JSON) |
| 4–6 | Type hints, dataclasses, OOP, generators, context managers, `collections` | Fully typed code (`mypy --strict`) · LeetCode in Python |
| 7–10 | FastAPI, Pydantic, asyncio, SQLAlchemy + Alembic, JWT auth with `Depends` | Notes API rebuilt in FastAPI with Postgres and login |
| 11–12 | pandas, pytest | Reports service (CSV export) for the Expense Tracker + tests |
| 13–16 | Docker, deployment, background jobs, the GIL, performance | A Python service inside Project 2 · Python interview review |

**Tip:** solve the weekly LeetCode problems in **both** JavaScript and Python. Many companies let you pick the language for coding rounds, and Python is often faster to write.

---

## All weeks

### October 2026

| Week | Dates | Focus | Files |
|---|---|---|---|
| 1 | Thu Oct 15 – Sun Oct 18, 2026 **(current week)** | Restart and JS core | [Plan](2026-10-October/Week-01_Oct-15-to-Oct-18/plan.md) · [Quiz](2026-10-October/Week-01_Oct-15-to-Oct-18/quiz.md) · [Interview](2026-10-October/Week-01_Oct-15-to-Oct-18/interview-prep.md) |
| 2 | Mon Oct 19 – Sun Oct 25, 2026 **(upcoming week)** | Objects, async and the DOM | [Plan](2026-10-October/Week-02_Oct-19-to-Oct-25/plan.md) · [Quiz](2026-10-October/Week-02_Oct-19-to-Oct-25/quiz.md) · [Interview](2026-10-October/Week-02_Oct-19-to-Oct-25/interview-prep.md) |
| 3 | Mon Oct 26 – Sun Nov 1, 2026 | Git, modules and vanilla projects | [Plan](2026-10-October/Week-03_Oct-26-to-Nov-01/plan.md) · [Quiz](2026-10-October/Week-03_Oct-26-to-Nov-01/quiz.md) · [Interview](2026-10-October/Week-03_Oct-26-to-Nov-01/interview-prep.md) |

### November 2026

| Week | Dates | Focus | Files |
|---|---|---|---|
| 4 | Mon Nov 2 – Sun Nov 8, 2026 | TypeScript | [Plan](2026-11-November/Week-04_Nov-02-to-Nov-08/plan.md) · [Quiz](2026-11-November/Week-04_Nov-02-to-Nov-08/quiz.md) · [Interview](2026-11-November/Week-04_Nov-02-to-Nov-08/interview-prep.md) |
| 5 | Mon Nov 9 – Sun Nov 15, 2026 | React core | [Plan](2026-11-November/Week-05_Nov-09-to-Nov-15/plan.md) · [Quiz](2026-11-November/Week-05_Nov-09-to-Nov-15/quiz.md) · [Interview](2026-11-November/Week-05_Nov-09-to-Nov-15/interview-prep.md) |
| 6 | Mon Nov 16 – Sun Nov 22, 2026 | React intermediate | [Plan](2026-11-November/Week-06_Nov-16-to-Nov-22/plan.md) · [Quiz](2026-11-November/Week-06_Nov-16-to-Nov-22/quiz.md) · [Interview](2026-11-November/Week-06_Nov-16-to-Nov-22/interview-prep.md) |
| 7 | Mon Nov 23 – Sun Nov 29, 2026 | Node.js and Express | [Plan](2026-11-November/Week-07_Nov-23-to-Nov-29/plan.md) · [Quiz](2026-11-November/Week-07_Nov-23-to-Nov-29/quiz.md) · [Interview](2026-11-November/Week-07_Nov-23-to-Nov-29/interview-prep.md) |

### December 2026

| Week | Dates | Focus | Files |
|---|---|---|---|
| 8 | Mon Nov 30 – Sun Dec 6, 2026 | MongoDB + Mongoose | [Plan](2026-12-December/Week-08_Nov-30-to-Dec-06/plan.md) · [Quiz](2026-12-December/Week-08_Nov-30-to-Dec-06/quiz.md) · [Interview](2026-12-December/Week-08_Nov-30-to-Dec-06/interview-prep.md) |
| 9 | Mon Dec 7 – Sun Dec 13, 2026 | SQL + PostgreSQL | [Plan](2026-12-December/Week-09_Dec-07-to-Dec-13/plan.md) · [Quiz](2026-12-December/Week-09_Dec-07-to-Dec-13/quiz.md) · [Interview](2026-12-December/Week-09_Dec-07-to-Dec-13/interview-prep.md) |
| 10 | Mon Dec 14 – Sun Dec 20, 2026 | Authentication and security | [Plan](2026-12-December/Week-10_Dec-14-to-Dec-20/plan.md) · [Quiz](2026-12-December/Week-10_Dec-14-to-Dec-20/quiz.md) · [Interview](2026-12-December/Week-10_Dec-14-to-Dec-20/interview-prep.md) |
| 11 | Mon Dec 21 – Sun Dec 27, 2026 | Project 1: Expense Tracker (fullstack) | [Plan](2026-12-December/Week-11_Dec-21-to-Dec-27/plan.md) · [Quiz](2026-12-December/Week-11_Dec-21-to-Dec-27/quiz.md) · [Interview](2026-12-December/Week-11_Dec-21-to-Dec-27/interview-prep.md) |
| 12 | Mon Dec 28, 2026 – Sun Jan 3, 2027 | Testing + finishing Project 1 | [Plan](2026-12-December/Week-12_Dec-28-to-Jan-03/plan.md) · [Quiz](2026-12-December/Week-12_Dec-28-to-Jan-03/quiz.md) · [Interview](2026-12-December/Week-12_Dec-28-to-Jan-03/interview-prep.md) |

### January 2027

| Week | Dates | Focus | Files |
|---|---|---|---|
| 13 | Mon Jan 4 – Sun Jan 10, 2027 | Next.js + deployment | [Plan](2027-01-January/Week-13_Jan-04-to-Jan-10/plan.md) · [Quiz](2027-01-January/Week-13_Jan-04-to-Jan-10/quiz.md) · [Interview](2027-01-January/Week-13_Jan-04-to-Jan-10/interview-prep.md) |
| 14 | Mon Jan 11 – Sun Jan 17, 2027 | Project 2: Portfolio-grade app | [Plan](2027-01-January/Week-14_Jan-11-to-Jan-17/plan.md) · [Quiz](2027-01-January/Week-14_Jan-11-to-Jan-17/quiz.md) · [Interview](2027-01-January/Week-14_Jan-11-to-Jan-17/interview-prep.md) |
| 15 | Mon Jan 18 – Sun Jan 24, 2027 | Finish Project 2 + system design basics | [Plan](2027-01-January/Week-15_Jan-18-to-Jan-24/plan.md) · [Quiz](2027-01-January/Week-15_Jan-18-to-Jan-24/quiz.md) · [Interview](2027-01-January/Week-15_Jan-18-to-Jan-24/interview-prep.md) |
| 16 | Mon Jan 25 – Sun Jan 31, 2027 | Interview sprint | [Plan](2027-01-January/Week-16_Jan-25-to-Jan-31/plan.md) · [Quiz](2027-01-January/Week-16_Jan-25-to-Jan-31/quiz.md) · [Interview](2027-01-January/Week-16_Jan-25-to-Jan-31/interview-prep.md) |

---

## Score tracker

| Week | Quiz score | Retake score | Weak topics to review |
|---|---|---|---|
| 1 | /11 | /11 | |
| 2 | /11 | /11 | |
| 3 | /8 | /8 | |
| 4 | /8 | /8 | |
| 5 | /8 | /8 | |
| 6 | /9 | /9 | |
| 7 | /9 | /9 | |
| 8 | /7 | /7 | |
| 9 | /7 | /7 | |
| 10 | /8 | /8 | |
| 11 | /7 | /7 | |
| 12 | /7 | /7 | |
| 13 | /6 | /6 | |
| 14 | /5 | /5 | |
| 15 | /7 | /7 | |
| 16 | /8 | /8 | |

**Retake schedule:** Weeks 1–2 on Nov 1 · Weeks 4–6 on Nov 29 · Weeks 7–11 on Jan 3 · all of them on Jan 31. **Target: 80% or more.**
