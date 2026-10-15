# Week 9 · Quiz: SQL + PostgreSQL

**Mon Dec 7 – Sun Dec 13, 2026**

[← Back to roadmap](../../README.md) · [Plan](plan.md) · [Quiz](quiz.md) · [Interview prep](interview-prep.md)

> Answer **in your head or on paper first**, then open the answer. No AI, no Google. ✍️ = write code by hand.

**Q1.** INNER JOIN vs LEFT JOIN?
<details><summary>Answer</summary>

INNER returns only rows that match in both tables. LEFT returns all rows from the left table, with NULLs where the right table has no match.
</details>

**Q2.** ✍️ SQL: total amount spent per category for user 1, highest first.
<details><summary>Answer</summary>

```sql
SELECT category, SUM(amount) AS total
FROM expenses
WHERE user_id = 1
GROUP BY category
ORDER BY total DESC;
```
</details>

**Q3.** `WHERE` vs `HAVING`?
<details><summary>Answer</summary>

`WHERE` filters rows **before** grouping. `HAVING` filters groups **after** `GROUP BY` (for example `HAVING SUM(amount) > 100`).
</details>

**Q4.** What are the ACID properties?
<details><summary>Answer</summary>

Atomicity (all or nothing), Consistency (the rules always hold), Isolation (concurrent transactions don't interfere), Durability (committed data survives a crash).
</details>

**Q5.** ✍️ Why is this dangerous, and how do you fix it?
```js
db.query(`SELECT * FROM users WHERE email = '${email}'`);
```
<details><summary>Answer</summary>

It allows SQL injection. Use a parameterized query instead:
```js
db.query('SELECT * FROM users WHERE email = $1', [email]);
```
</details>

## 🐍 Python track

**Q6.** How do you avoid the N+1 problem in SQLAlchemy?
<details><summary>Answer</summary>

Load relationships eagerly: `selectinload()` (a second query with `IN`) or `joinedload()` (a JOIN) in the query options.
</details>

**Q7.** What is Alembic for?
<details><summary>Answer</summary>

Database migrations: versioned scripts that change the schema step by step (and can roll back), so every environment's database matches the code.
</details>

---

**My score:** ___ / 7  ·  **Date:** ______  ·  **Retake score:** ___ / 7
