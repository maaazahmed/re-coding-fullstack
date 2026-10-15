# Week 11 · Quiz: Project 1: Expense Tracker (fullstack)

**Mon Dec 21 – Sun Dec 27, 2026**

[← Back to roadmap](../../README.md) · [Plan](plan.md) · [Quiz](quiz.md) · [Interview prep](interview-prep.md)

> Answer **in your head or on paper first**, then open the answer. No AI, no Google. ✍️ = write code by hand.

**Q1.** You need to store money amounts. Which data type do you use, and why not `float`?
<details><summary>Answer</summary>

Use `NUMERIC(12,2)` in Postgres, or store an integer amount in cents. Floats can't represent decimals exactly (`0.1 + 0.2 !== 0.3`), so totals drift.
</details>

**Q2.** A user requests `GET /expenses/42`, but expense 42 belongs to another user. What should happen, and where do you check it?
<details><summary>Answer</summary>

Return 404 (or 403). Check ownership in the backend query itself, for example `WHERE id = $1 AND user_id = $2`. Never trust the frontend to hide it.
</details>

**Q3.** Where should validation happen: frontend, backend, or both?
<details><summary>Answer</summary>

Both. Frontend validation is for user experience. Backend validation is for security and correctness, because anyone can call your API directly.
</details>

**Q4.** How do you keep API URLs and secrets out of your code?
<details><summary>Answer</summary>

Environment variables: `.env` locally (added to `.gitignore`), and the hosting provider's env settings in production. On the frontend, only public values (Vite's `VITE_` prefix); never secrets.
</details>

**Q5.** What's the difference between a loading state, an error state and an empty state? Why do you need all three?
<details><summary>Answer</summary>

Loading: data is on its way. Error: the request failed (show a message and a retry option). Empty: the request succeeded but there's no data (show a helpful prompt). Without them, users see a blank or broken screen.
</details>

## 🐍 Python track

**Q6.** ✍️ With pandas, total `amount` by `category` from a DataFrame `df`, highest first.
<details><summary>Answer</summary>

```python
totals = df.groupby("category")["amount"].sum().sort_values(ascending=False)
```
</details>

**Q7.** Your app has a Node backend and a Python service. How should they share data?
<details><summary>Answer</summary>

Either both read the same database (simple, but they become coupled to the schema), or the Python service exposes an API that the Node backend or the frontend calls. Keep one owner for each table.
</details>

---

**My score:** ___ / 7  ·  **Date:** ______  ·  **Retake score:** ___ / 7
