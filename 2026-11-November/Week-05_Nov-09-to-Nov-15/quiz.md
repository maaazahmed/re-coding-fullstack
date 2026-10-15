# Week 5 · Quiz: React core

**Mon Nov 9 – Sun Nov 15, 2026**

[← Back to roadmap](../../README.md) · [Plan](plan.md) · [Quiz](quiz.md) · [Interview prep](interview-prep.md)

> Answer **in your head or on paper first**, then open the answer. No AI, no Google. ✍️ = write code by hand.

**Q1.** Why does React need `key` on list items? Why is using the index as a key bad?
<details><summary>Answer</summary>

Keys let React match items between renders. If you reorder, insert or delete items, index keys cause wrong DOM reuse and state bugs. Use a stable unique id instead.
</details>

**Q2.** When does `useEffect` run with `[]`, `[dep]` and no array at all?
<details><summary>Answer</summary>

`[]` runs once after mount (plus cleanup on unmount). `[dep]` runs after mount and whenever `dep` changes. With no array it runs after **every** render.
</details>

**Q3.** What is the cleanup function in `useEffect` for?
<details><summary>Answer</summary>

It runs before the effect runs again and on unmount. Use it to clear timers, unsubscribe, abort fetches or remove listeners, which prevents memory leaks and race conditions.
</details>

**Q4.** Controlled vs uncontrolled components?
<details><summary>Answer</summary>

In a controlled component, React state owns the input value (`value` + `onChange`). In an uncontrolled one, the DOM owns it and you read it with a `ref` or `FormData`.
</details>

**Q5.** Why is `setCount(count + 1)` called 3 times in a row only +1? How do you fix it?
<details><summary>Answer</summary>

All three calls read the same `count` from that render. Use a functional update instead: `setCount(c => c + 1)`.
</details>

**Q6.** ✍️ Remove the todo with `id` from state without mutating it.
<details><summary>Answer</summary>

```ts
setTodos(prev => prev.filter(t => t.id !== id));
```
</details>

## 🐍 Python track

**Q7.** `__str__` vs `__repr__`?
<details><summary>Answer</summary>

`__str__` is the readable version for users (`print`). `__repr__` is the unambiguous version for developers (the REPL, debugging), ideally looking like code that recreates the object.
</details>

**Q8.** `@classmethod` vs `@staticmethod`?
<details><summary>Answer</summary>

A classmethod receives the class (`cls`), so it's used for alternative constructors like `User.from_dict(...)`. A staticmethod receives nothing; it's just a function grouped inside the class.
</details>

---

**My score:** ___ / 8  ·  **Date:** ______  ·  **Retake score:** ___ / 8
