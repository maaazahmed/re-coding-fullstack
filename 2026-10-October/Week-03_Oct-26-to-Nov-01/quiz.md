# Week 3 · Quiz: Git, modules and vanilla projects

**Mon Oct 26 – Sun Nov 1, 2026**

[← Back to roadmap](../../README.md) · [Plan](plan.md) · [Quiz](quiz.md) · [Interview prep](interview-prep.md)

> Answer **in your head or on paper first**, then open the answer. No AI, no Google. ✍️ = write code by hand.

**Q1.** `git merge` vs `git rebase`?
<details><summary>Answer</summary>

Merge keeps the history and creates a merge commit. Rebase replays your commits on top of the other branch, which gives a linear history. Don't rebase shared or public branches.
</details>

**Q2.** `git revert` vs `git reset`?
<details><summary>Answer</summary>

`revert` creates a **new commit** that undoes an earlier one, which is safe on shared branches. `reset` moves the branch pointer back (and with `--hard`, discards changes), which rewrites history.
</details>

**Q3.** ES modules vs CommonJS?
<details><summary>Answer</summary>

CommonJS: `require`/`module.exports`, loaded synchronously, the older Node default. ES modules: `import`/`export`, statically analyzable (tree-shaking), the browser standard and the modern Node default with `"type": "module"`.
</details>

**Q4.** `dependencies` vs `devDependencies`?
<details><summary>Answer</summary>

`dependencies` are needed at runtime (express, react). `devDependencies` are only needed for development and building (typescript, vitest, eslint).
</details>

**Q5.** What can you store in `localStorage`? What are its limits?
<details><summary>Answer</summary>

Only strings (use `JSON.stringify`/`JSON.parse` for objects), about 5MB per origin. It is synchronous, it never expires, and any script on the page can read it, so never store secrets there.
</details>

**Q6.** ✍️ Safely read a JSON value from `localStorage` with a fallback if it's missing or broken.
<details><summary>Answer</summary>

```js
function load(key, fallback) {
  try {
    const raw = localStorage.getItem(key);
    return raw ? JSON.parse(raw) : fallback;
  } catch {
    return fallback;
  }
}
```
</details>

## 🐍 Python track

**Q7.** What does `if __name__ == "__main__":` do?
<details><summary>Answer</summary>

The code inside runs only when the file is executed directly, not when it is imported as a module.
</details>

**Q8.** Why use a virtual environment?
<details><summary>Answer</summary>

It isolates each project's packages and versions, so projects don't conflict with each other or with the system Python. `uv` creates and manages it for you.
</details>

---

**My score:** ___ / 8  ·  **Date:** ______  ·  **Retake score:** ___ / 8
