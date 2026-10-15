# Week 16 · Quiz: Interview sprint

**Mon Jan 25 – Sun Jan 31, 2027**

[← Back to roadmap](../../README.md) · [Plan](plan.md) · [Quiz](quiz.md) · [Interview prep](interview-prep.md)

> Answer **in your head or on paper first**, then open the answer. No AI, no Google. ✍️ = write code by hand.

**Q1.** Explain the event loop in under 2 minutes, with the order of sync code, microtasks and macrotasks.
<details><summary>Answer</summary>

Sync code runs on the call stack first. When the stack is empty, **all** microtasks run (promise callbacks, `queueMicrotask`), then **one** macrotask (setTimeout, I/O), then microtasks again, and so on.
</details>

**Q2.** A React list is slow with 10,000 rows. Give 3 fixes.
<details><summary>Answer</summary>

Virtualize the list (only render visible rows, e.g. TanStack Virtual), paginate or load more, and memoize row components with stable keys and props.
</details>

**Q3.** An API endpoint got slow as the data grew. How do you investigate?
<details><summary>Answer</summary>

Measure first (logs, timing, APM). Check the DB query with `EXPLAIN` for missing indexes or N+1 queries, add pagination, then caching for hot data.
</details>

**Q4.** A user says "I logged in but I'm logged out after refresh." What could be wrong?
<details><summary>Answer</summary>

The token is only kept in memory/state, the cookie isn't set (wrong `SameSite`/`Secure`/domain, missing `credentials: 'include'`), or the refresh flow is broken.
</details>

**Q5.** What is the difference between authentication and authorization?
<details><summary>Answer</summary>

Authentication: who are you? (login, 401 if missing). Authorization: what are you allowed to do? (roles and ownership, 403 if not allowed).
</details>

## 🐍 Python track

**Q6.** What does this print?
```python
grid = [[0] * 3] * 3
grid[0][0] = 1
print(grid)
```
<details><summary>Answer</summary>

`[[1, 0, 0], [1, 0, 0], [1, 0, 0]]`. The outer `* 3` copies the **same** inner list 3 times. Use `[[0] * 3 for _ in range(3)]` instead.
</details>

**Q7.** What is the LEGB rule?
<details><summary>Answer</summary>

The order Python looks up names: **L**ocal → **E**nclosing (outer functions) → **G**lobal (module) → **B**uilt-in.
</details>

**Q8.** Shallow vs deep copy in Python?
<details><summary>Answer</summary>

`list.copy()`, `copy.copy()` and slicing make a shallow copy (nested objects are shared). `copy.deepcopy()` copies everything recursively.
</details>

---

**My score:** ___ / 8  ·  **Date:** ______  ·  **Retake score:** ___ / 8
