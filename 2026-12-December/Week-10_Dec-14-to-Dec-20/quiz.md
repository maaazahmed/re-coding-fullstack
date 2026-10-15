# Week 10 · Quiz: Authentication and security

**Mon Dec 14 – Sun Dec 20, 2026**

[← Back to roadmap](../../README.md) · [Plan](plan.md) · [Quiz](quiz.md) · [Interview prep](interview-prep.md)

> Answer **in your head or on paper first**, then open the answer. No AI, no Google. ✍️ = write code by hand.

**Q1.** Why hash passwords instead of encrypting them? Why use bcrypt and not SHA-256?
<details><summary>Answer</summary>

Hashing is one-way, so even you can't recover the password. bcrypt is deliberately **slow** and salted, which makes brute-force attacks hard. SHA-256 is too fast.
</details>

**Q2.** What are the 3 parts of a JWT? Is the payload secret?
<details><summary>Answer</summary>

Header, payload and signature. The payload is only base64-encoded, **not** encrypted, so never put secrets in it. The signature proves the token wasn't changed.
</details>

**Q3.** Should you store a JWT in localStorage or in an httpOnly cookie?
<details><summary>Answer</summary>

localStorage can be read by JavaScript, so it is vulnerable to XSS. An httpOnly cookie can't be read by JavaScript, but it needs CSRF protection (`SameSite`, CSRF tokens). Usually: a short-lived access token plus a refresh token in an httpOnly cookie.
</details>

**Q4.** What is CORS? Who enforces it?
<details><summary>Answer</summary>

Cross-Origin Resource Sharing. The **browser** enforces it. The server sends headers such as `Access-Control-Allow-Origin` to allow other origins. Postman and curl ignore CORS.
</details>

**Q5.** What are XSS, CSRF and SQL injection? Give one defense for each.
<details><summary>Answer</summary>

XSS: injected scripts. Defense: escape output, CSP, React's automatic escaping. CSRF: forged requests that use the user's cookies. Defense: SameSite cookies, CSRF tokens. SQL injection: malicious SQL in user input. Defense: parameterized queries or an ORM.
</details>

**Q6.** Sessions vs JWT?
<details><summary>Answer</summary>

Sessions: the server stores the state and the client holds a session id cookie; easy to revoke. JWT: stateless and self-contained, so it scales easily, but it is hard to revoke before it expires.
</details>

## 🐍 Python track

**Q7.** What is `Depends` in FastAPI? Give an example of where you'd use it.
<details><summary>Answer</summary>

Dependency injection: FastAPI runs the dependency function and passes its result into your route. Examples: a database session per request, or `get_current_user` to protect routes.
</details>

**Q8.** ✍️ Write the signature of a protected FastAPI route that needs the current user.
<details><summary>Answer</summary>

```python
@app.get("/notes")
def list_notes(user: User = Depends(get_current_user)):
    ...
```
</details>

---

**My score:** ___ / 8  ·  **Date:** ______  ·  **Retake score:** ___ / 8
