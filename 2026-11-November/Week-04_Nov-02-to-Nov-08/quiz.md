# Week 4 · Quiz: TypeScript

**Mon Nov 2 – Sun Nov 8, 2026**

[← Back to roadmap](../../README.md) · [Plan](plan.md) · [Quiz](quiz.md) · [Interview prep](interview-prep.md)

> Answer **in your head or on paper first**, then open the answer. No AI, no Google. ✍️ = write code by hand.

**Q1.** `interface` vs `type` in TypeScript?
<details><summary>Answer</summary>

Both describe object shapes. Interfaces can be merged (declared twice) and extended. Types can describe unions, primitives, tuples and mapped types. A common convention: `interface` for objects, `type` for unions and other complex types.
</details>

**Q2.** `any` vs `unknown`?
<details><summary>Answer</summary>

`any` turns off type checking. `unknown` is type-safe: you must narrow it (with `typeof`, `instanceof` or a type guard) before you can use it.
</details>

**Q3.** ✍️ Write a generic function `first<T>(arr: T[]): T | undefined`.
<details><summary>Answer</summary>

```ts
function first<T>(arr: T[]): T | undefined {
  return arr[0];
}
```
</details>

**Q4.** What do `Partial<User>`, `Pick<User, 'id' | 'name'>` and `Omit<User, 'password'>` produce?
<details><summary>Answer</summary>

`Partial` makes every property optional (useful for update payloads). `Pick` keeps only the listed properties. `Omit` removes the listed properties (for example, a public user without the password).
</details>

**Q5.** ✍️ Write a type guard `isString(x: unknown)`.
<details><summary>Answer</summary>

```ts
function isString(x: unknown): x is string {
  return typeof x === 'string';
}
```
</details>

**Q6.** What does `strict: true` turn on, most importantly?
<details><summary>Answer</summary>

`strictNullChecks` (`null`/`undefined` must be handled), `noImplicitAny`, strict function types and more. It catches many real bugs at compile time.
</details>

## 🐍 Python track

**Q7.** Are Python type hints checked when the code runs?
<details><summary>Answer</summary>

No. Python ignores them at runtime. Tools like mypy or pyright check them before you run the code, and libraries like Pydantic use them for runtime validation.
</details>

**Q8.** What does `@dataclass` give you?
<details><summary>Answer</summary>

An automatic `__init__`, `__repr__` and `__eq__` from the annotated fields. Options: `frozen=True` (immutable), `order=True`, `slots=True`.
</details>

---

**My score:** ___ / 8  ·  **Date:** ______  ·  **Retake score:** ___ / 8
