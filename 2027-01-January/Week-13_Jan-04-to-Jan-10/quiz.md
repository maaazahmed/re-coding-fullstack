# Week 13 · Quiz: Next.js + deployment

**Mon Jan 4 – Sun Jan 10, 2027**

[← Back to roadmap](../../README.md) · [Plan](plan.md) · [Quiz](quiz.md) · [Interview prep](interview-prep.md)

> Answer **in your head or on paper first**, then open the answer. No AI, no Google. ✍️ = write code by hand.

**Q1.** Server components vs client components in Next.js?
<details><summary>Answer</summary>

Server components run on the server: no JavaScript is shipped to the browser and they can access the DB or secrets directly. Client components (`'use client'`) run in the browser and can use state, effects and event handlers.
</details>

**Q2.** CSR vs SSR vs SSG vs ISR?
<details><summary>Answer</summary>

CSR renders in the browser. SSR renders on the server for each request. SSG renders at build time. ISR is static, but regenerated after a time interval or on demand.
</details>

**Q3.** Your app works locally but the API calls fail after deploying. Name 3 likely causes.
<details><summary>Answer</summary>

Missing or wrong environment variables in production, CORS not allowing the production frontend URL, and the frontend still pointing to `localhost`. Also check HTTPS/cookie settings (`Secure`, `SameSite`).
</details>

**Q4.** Why shouldn't you put a database password in a client component?
<details><summary>Answer</summary>

Everything in a client component is shipped to the browser, so anyone can read it. Secrets must stay on the server (server components, route handlers, the backend).
</details>

## 🐍 Python track

**Q5.** ✍️ Write a minimal Dockerfile for a FastAPI app (`main.py`, `requirements.txt`).
<details><summary>Answer</summary>

```dockerfile
FROM python:3.14-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY . .
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
```
</details>

**Q6.** Why copy `requirements.txt` and install **before** copying the rest of the code?
<details><summary>Answer</summary>

Docker caches each layer. Dependencies change rarely, so this layer is reused and rebuilds are fast when only your code changes.
</details>

---

**My score:** ___ / 6  ·  **Date:** ______  ·  **Retake score:** ___ / 6
