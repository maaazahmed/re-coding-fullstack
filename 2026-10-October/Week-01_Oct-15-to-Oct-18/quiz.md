# Week 1 · Quiz: Restart and JS core

**Thu Oct 15 – Sun Oct 18, 2026 (current week)**

[← Back to roadmap](../../README.md) · [Plan](plan.md) · [Quiz](quiz.md) · [Interview prep](interview-prep.md)

> Answer **in your head or on paper first**, then open the answer. No AI, no Google. ✍️ = write code by hand.

**Q1.** What is the difference between `let`, `const` and `var`?
<details><summary>Answer</summary>

`var` is function-scoped, hoisted and initialized as `undefined`, and can be redeclared. `let` and `const` are block-scoped and hoisted, but they sit in the "temporal dead zone" until their declaration runs. `const` cannot be reassigned, but objects declared with `const` can still be mutated.
</details>

**Q2.** What does this print?
```js
console.log(a);
var a = 5;
console.log(b);
let b = 5;
```
<details><summary>Answer</summary>

`undefined`, then a `ReferenceError` (`b` is in the temporal dead zone).
</details>

**Q3.** What is a closure? Give a real use case.
<details><summary>Answer</summary>

A function that remembers the variables from the scope where it was created, even after that outer function has returned. Use cases: private counters, `once()`, debounce, memoization, factory functions.
</details>

**Q4.** ✍️ Write `once(fn)`: it returns a function that runs `fn` only the first time it is called and returns the cached result afterwards.
<details><summary>Answer</summary>

```js
function once(fn) {
  let called = false, result;
  return (...args) => {
    if (!called) { called = true; result = fn(...args); }
    return result;
  };
}
```
</details>

**Q5.** `==` vs `===`?
<details><summary>Answer</summary>

`==` converts types before comparing (`'1' == 1` is true). `===` compares value **and** type with no conversion. Always use `===`.
</details>

**Q6.** ✍️ Using `reduce`, group `[{name:'a', role:'dev'}, {name:'b', role:'qa'}, {name:'c', role:'dev'}]` by `role`.
<details><summary>Answer</summary>

```js
const grouped = users.reduce((acc, u) => {
  (acc[u.role] ??= []).push(u);
  return acc;
}, {});
```
</details>

**Q7.** What do `null`, `undefined` and an undeclared variable mean?
<details><summary>Answer</summary>

`undefined` means declared but not assigned. `null` is an intentional "no value". Undeclared means it was never declared, and accessing it throws a `ReferenceError`.
</details>

**Q8.** What does `[1, 2, 3].map(parseInt)` return? Why?
<details><summary>Answer</summary>

`[1, NaN, NaN]`. `map` passes `(value, index)`, so the calls are `parseInt('2', 1)` and `parseInt('3', 2)`, which use invalid radixes.
</details>

## 🐍 Python track

**Q9.** Mutable vs immutable types in Python? Give 3 of each.
<details><summary>Answer</summary>

Mutable (can change in place): `list`, `dict`, `set`. Immutable: `int`, `str`, `tuple` (also `float`, `bool`, `frozenset`). Only immutable (hashable) values can be dict keys or set items.
</details>

**Q10.** ✍️ With a list comprehension, get the squares of the even numbers in `nums`.
<details><summary>Answer</summary>

```python
squares = [n * n for n in nums if n % 2 == 0]
```
</details>

**Q11.** `is` vs `==`?
<details><summary>Answer</summary>

`==` compares **values**. `is` checks whether two names point to the **same object**. Use `is` only for `None` (`if x is None`).
</details>

---

**My score:** ___ / 11  ·  **Date:** ______  ·  **Retake score:** ___ / 11
