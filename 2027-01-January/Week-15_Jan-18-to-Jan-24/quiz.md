# Week 15 · Quiz: Finish Project 2 + system design basics

**Mon Jan 18 – Sun Jan 24, 2027**

[← Back to roadmap](../../README.md) · [Plan](plan.md) · [Quiz](quiz.md) · [Interview prep](interview-prep.md)

> Answer **in your head or on paper first**, then open the answer. No AI, no Google. ✍️ = write code by hand.

**Q1.** What is caching? Name 3 layers where you can cache.
<details><summary>Answer</summary>

Storing results to avoid repeating work. Layers: the browser/HTTP cache, a CDN, the app or Redis, and the DB query cache.
</details>

**Q2.** Horizontal vs vertical scaling?
<details><summary>Answer</summary>

Vertical: a bigger machine. Horizontal: more machines behind a load balancer. Horizontal scaling needs stateless servers.
</details>

**Q3.** What is rate limiting? How would you implement it?
<details><summary>Answer</summary>

Limiting the number of requests a client can make per time window. Implement it with a token bucket or sliding window algorithm, with counters in Redis keyed by IP or user.
</details>

**Q4.** Design a URL shortener in 5 bullet points.
<details><summary>Answer</summary>

- `POST /shorten` generates a short code (base62 of an ID, or a random string) and stores code → URL
- `GET /:code` looks up the code and responds with a 301/302 redirect
- Store in a DB with an index on `code`, and cache popular codes in Redis
- Handle collisions, expiry and analytics (click counts) asynchronously with a queue
- Rate-limit creation, and scale reads with a cache and replicas
</details>

**Q5.** Why would you put a message queue between two services?
<details><summary>Answer</summary>

To decouple them and do slow work in the background (emails, image processing), to absorb traffic spikes, and to retry failed jobs without losing them.
</details>

## 🐍 Python track

**Q6.** What is the GIL, and how does it affect your choice of concurrency tool?
<details><summary>Answer</summary>

The Global Interpreter Lock lets only one thread run Python bytecode at a time (in the default build). For I/O-bound work use asyncio or threads. For CPU-bound work use multiprocessing (or the free-threaded build).
</details>

**Q7.** Time complexity of `x in my_list` vs `x in my_set`?
<details><summary>Answer</summary>

List: O(n), it checks each item. Set: O(1) on average, using a hash lookup.
</details>

---

**My score:** ___ / 7  ·  **Date:** ______  ·  **Retake score:** ___ / 7
