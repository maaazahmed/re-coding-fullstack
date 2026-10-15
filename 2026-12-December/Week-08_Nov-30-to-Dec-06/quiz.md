# Week 8 · Quiz: MongoDB + Mongoose

**Mon Nov 30 – Sun Dec 6, 2026**

[← Back to roadmap](../../README.md) · [Plan](plan.md) · [Quiz](quiz.md) · [Interview prep](interview-prep.md)

> Answer **in your head or on paper first**, then open the answer. No AI, no Google. ✍️ = write code by hand.

**Q1.** SQL vs NoSQL: when do you choose each?
<details><summary>Answer</summary>

SQL: structured relational data, joins, strong consistency and transactions (payments, orders). NoSQL (MongoDB): flexible or nested documents, fast iteration, and data you usually read as a whole document.
</details>

**Q2.** Embedding vs referencing in MongoDB?
<details><summary>Answer</summary>

Embed when the data is always read together and bounded in size (an address inside a user). Reference when it is large, grows without limit, or is shared between documents (a user's posts).
</details>

**Q3.** What is the N+1 query problem?
<details><summary>Answer</summary>

You make 1 query for a list, then N more queries for each item's relation. Fix it with a JOIN, `populate`/`include`, or batching.
</details>

**Q4.** Offset pagination vs cursor pagination?
<details><summary>Answer</summary>

Offset (`skip`/`limit`, `?page=3`) is simple but slow on big data and can skip or repeat items when data changes. Cursor (`?after=<lastId>`) is fast and stable, but you can't jump to page N.
</details>

**Q5.** What is an index? What is its downside?
<details><summary>Answer</summary>

A data structure (usually a B-tree) that makes lookups fast. Downsides: it uses extra storage and makes writes slower.
</details>

## 🐍 Python track

**Q6.** How is Python's asyncio similar to the JS event loop, and how is it different?
<details><summary>Answer</summary>

Both run on one thread and switch tasks at `await` points while waiting for I/O. Differences: in JS the event loop is always running and most I/O is async by default; in Python you start the loop yourself (`asyncio.run`), and a normal blocking call like `requests.get` blocks the whole loop.
</details>

**Q7.** ✍️ Fetch a list of URLs concurrently with `httpx` and return the status codes.
<details><summary>Answer</summary>

```python
import asyncio
import httpx

async def fetch_all(urls: list[str]) -> list[int]:
    async with httpx.AsyncClient() as client:
        responses = await asyncio.gather(*(client.get(u) for u in urls))
    return [r.status_code for r in responses]
```
</details>

---

**My score:** ___ / 7  ·  **Date:** ______  ·  **Retake score:** ___ / 7
