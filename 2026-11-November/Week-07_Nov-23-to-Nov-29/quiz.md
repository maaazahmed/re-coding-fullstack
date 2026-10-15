# Week 7 · Quiz: Node.js and Express

**Mon Nov 23 – Sun Nov 29, 2026**

[← Back to roadmap](../../README.md) · [Plan](plan.md) · [Quiz](quiz.md) · [Interview prep](interview-prep.md)

> Answer **in your head or on paper first**, then open the answer. No AI, no Google. ✍️ = write code by hand.

**Q1.** What is middleware in Express? Write a logger middleware.
<details><summary>Answer</summary>

Middleware is a function `(req, res, next)` that runs in the request pipeline. It can modify `req`/`res`, end the response, or call `next()`.
```js
app.use((req, res, next) => {
  console.log(req.method, req.url);
  next();
});
```
</details>

**Q2.** What is the signature of an Express error handler?
<details><summary>Answer</summary>

It has 4 arguments: `(err, req, res, next)`. Register it **after** all routes.
</details>

**Q3.** Which status codes do you use for: created, bad input, not logged in, logged in but no permission, not found, server crash?
<details><summary>Answer</summary>

201, 400, 401, 403, 404, 500.
</details>

**Q4.** `PUT` vs `PATCH`?
<details><summary>Answer</summary>

`PUT` replaces the whole resource. `PATCH` partially updates it.
</details>

**Q5.** What is idempotency? Which HTTP methods are idempotent?
<details><summary>Answer</summary>

Making the same request many times has the same effect as making it once. `GET`, `PUT`, `DELETE`, `HEAD` and `OPTIONS` are idempotent. `POST` is not.
</details>

**Q6.** What does Node's single thread mean? How does it handle many requests?
<details><summary>Answer</summary>

JavaScript runs on one thread, but I/O is non-blocking (handled by libuv and the OS). While it waits for I/O, the event loop handles other requests. CPU-heavy work blocks it, so use worker threads for that.
</details>

**Q7.** `req.params` vs `req.query` vs `req.body`?
<details><summary>Answer</summary>

`params`: path segments (`/notes/:id`). `query`: the URL query string (`?page=2`). `body`: the request payload (JSON), which needs `express.json()` middleware.
</details>

## 🐍 Python track

**Q8.** What does Pydantic do in FastAPI?
<details><summary>Answer</summary>

It validates and parses request data from type hints, returns a 422 error automatically for bad input, serializes responses, and generates the OpenAPI schema for `/docs`.
</details>

**Q9.** FastAPI vs Express: name 3 differences.
<details><summary>Answer</summary>

FastAPI validates from type hints automatically (Express needs Zod/Joi), generates interactive API docs for free, and has dependency injection (`Depends`). Express is more minimal, with a huge middleware ecosystem.
</details>

---

**My score:** ___ / 9  ·  **Date:** ______  ·  **Retake score:** ___ / 9
