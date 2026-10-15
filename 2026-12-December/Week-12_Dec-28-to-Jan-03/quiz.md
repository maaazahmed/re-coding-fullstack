# Week 12 · Quiz: Testing + finishing Project 1

**Mon Dec 28, 2026 – Sun Jan 3, 2027**

[← Back to roadmap](../../README.md) · [Plan](plan.md) · [Quiz](quiz.md) · [Interview prep](interview-prep.md)

> Answer **in your head or on paper first**, then open the answer. No AI, no Google. ✍️ = write code by hand.

**Q1.** Unit vs integration vs E2E tests?
<details><summary>Answer</summary>

Unit: one function or component in isolation. Integration: several parts together (an API route plus the DB). E2E: the full app in a browser, the way a user would use it (Playwright).
</details>

**Q2.** What is mocking, and when do you use it?
<details><summary>Answer</summary>

Replacing a real dependency (an API, the DB, time) with a fake one so tests are fast, isolated and predictable.
</details>

**Q3.** What is the Arrange-Act-Assert pattern?
<details><summary>Answer</summary>

Arrange: set up the data and state. Act: run the thing you're testing. Assert: check the result. It keeps every test readable and focused on one behavior.
</details>

**Q4.** In React Testing Library, why should you prefer `getByRole` over `getByTestId`?
<details><summary>Answer</summary>

It queries the way a real user (and a screen reader) finds elements, so your tests also check accessibility and don't break when the markup changes.
</details>

**Q5.** What should you test first in a fullstack app if you have little time?
<details><summary>Answer</summary>

The critical paths: authentication, the core business logic (for example, money totals) and permission checks. Not trivial code or third-party libraries.
</details>

## 🐍 Python track

**Q6.** What is a pytest fixture?
<details><summary>Answer</summary>

A function that prepares something a test needs (a database, a client, test data), injected by naming it as a test parameter. It can also clean up after the test with `yield`.
</details>

**Q7.** ✍️ Use `parametrize` to test `is_even` with 3 inputs.
<details><summary>Answer</summary>

```python
import pytest

@pytest.mark.parametrize("n, expected", [(2, True), (3, False), (0, True)])
def test_is_even(n, expected):
    assert is_even(n) == expected
```
</details>

---

**My score:** ___ / 7  ·  **Date:** ______  ·  **Retake score:** ___ / 7
