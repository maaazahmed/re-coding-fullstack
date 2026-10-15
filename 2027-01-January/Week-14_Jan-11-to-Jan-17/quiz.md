# Week 14 · Quiz: Project 2: Portfolio-grade app

**Mon Jan 11 – Sun Jan 17, 2027**

[← Back to roadmap](../../README.md) · [Plan](plan.md) · [Quiz](quiz.md) · [Interview prep](interview-prep.md)

> Answer **in your head or on paper first**, then open the answer. No AI, no Google. ✍️ = write code by hand.

**Q1.** WebSockets vs polling vs SSE?
<details><summary>Answer</summary>

Polling: the client asks again and again. SSE: the server pushes one-way over HTTP. WebSockets: two-way and persistent, which suits chat and games.
</details>

**Q2.** How should you handle file uploads in a web app?
<details><summary>Answer</summary>

Validate the type and size on the server, store files in object storage (S3, Vercel Blob, Cloudinary) instead of the DB, save only the URL/key in the DB, and for big files upload directly from the client with a signed URL.
</details>

**Q3.** Role-based access control: how do you implement "only admins can delete posts"?
<details><summary>Answer</summary>

Store a role on the user, put it in the session or JWT, and check it in backend middleware before the handler runs (403 if not allowed). Hiding the button in the UI is not enough.
</details>

**Q4.** How would you implement search on a list of posts?
<details><summary>Answer</summary>

Simple: `ILIKE '%term%'` (slow on big tables). Better: Postgres full-text search with an index, or MongoDB text indexes. At scale: a search engine like Elasticsearch/Meilisearch. On the frontend, debounce the input.
</details>

## 🐍 Python track

**Q5.** FastAPI `BackgroundTasks` vs a task queue (Celery/RQ/Dramatiq)?
<details><summary>Answer</summary>

`BackgroundTasks` runs simple work in the same process after the response is sent, but it's lost if the server restarts. A task queue runs jobs in separate workers with retries and persistence, which is better for heavy or important jobs.
</details>

---

**My score:** ___ / 5  ·  **Date:** ______  ·  **Retake score:** ___ / 5
