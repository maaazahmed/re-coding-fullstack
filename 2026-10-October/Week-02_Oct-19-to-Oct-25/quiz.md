# Week 2 · Quiz: Objects, async and the DOM

**Mon Oct 19 – Sun Oct 25, 2026 (upcoming week)**

[← Back to roadmap](../../README.md) · [Plan](plan.md) · [Quiz](quiz.md) · [Interview prep](interview-prep.md)

> Answer **in your head or on paper first**, then open the answer. No AI, no Google. ✍️ = write code by hand.

**Q1.** What does this print, and why?
```js
console.log('1');
setTimeout(() => console.log('2'), 0);
Promise.resolve().then(() => console.log('3'));
console.log('4');
```
<details><summary>Answer</summary>

`1 4 3 2`. Synchronous code runs first. Then the **microtask** queue runs (promises), then the **macrotask** queue (setTimeout).
</details>

**Q2.** What is the difference between `Promise.all` and `Promise.allSettled`?
<details><summary>Answer</summary>

`all` rejects as soon as **any** promise rejects. `allSettled` always waits for all of them and returns `{status, value/reason}` for each.
</details>

**Q3.** What is `this` inside an arrow function?
<details><summary>Answer</summary>

Arrow functions don't have their own `this`. They take it from the surrounding (lexical) scope. Calling `call`, `apply` or `bind` on them cannot change it.
</details>

**Q4.** Shallow copy vs deep copy? How do you deep-copy an object?
<details><summary>Answer</summary>

A shallow copy (`{...obj}`, `Object.assign`) copies only the top level, so nested objects are shared. For a deep copy use `structuredClone(obj)`. `JSON.parse(JSON.stringify(obj))` also works, but it loses Dates, functions and `undefined`.
</details>

**Q5.** What is event delegation?
<details><summary>Answer</summary>

You attach one listener to a parent element and use `event.target` to handle events from its children. This works because of event bubbling. It's efficient and it also works for elements added later.
</details>

**Q6.** ✍️ Write `debounce(fn, delay)`.
<details><summary>Answer</summary>

```js
function debounce(fn, delay) {
  let timer;
  return (...args) => {
    clearTimeout(timer);
    timer = setTimeout(() => fn(...args), delay);
  };
}
```
</details>

**Q7.** ✍️ Write `sleep(ms)` that you can use as `await sleep(1000)`.
<details><summary>Answer</summary>

```js
const sleep = (ms) => new Promise((resolve) => setTimeout(resolve, ms));
```
</details>

**Q8.** `call` vs `apply` vs `bind`?
<details><summary>Answer</summary>

All three set `this`. `call(thisArg, a, b)` calls immediately with separate arguments. `apply(thisArg, [a, b])` calls immediately with an array. `bind(thisArg)` returns a **new function** to call later.
</details>

## 🐍 Python track

**Q9.** What's the bug here?
```python
def add(item, items=[]):
    items.append(item)
    return items
```
<details><summary>Answer</summary>

The default list is created **once** when the function is defined and shared between calls, so items pile up. Use `items=None` and then `if items is None: items = []`.
</details>

**Q10.** ✍️ Write a `@timer` decorator that prints how long a function took.
<details><summary>Answer</summary>

```python
import time
from functools import wraps

def timer(fn):
    @wraps(fn)
    def wrapper(*args, **kwargs):
        start = time.perf_counter()
        result = fn(*args, **kwargs)
        print(f"{fn.__name__} took {time.perf_counter() - start:.4f}s")
        return result
    return wrapper
```
</details>

**Q11.** What are `*args` and `**kwargs`?
<details><summary>Answer</summary>

`*args` collects extra positional arguments into a tuple. `**kwargs` collects extra keyword arguments into a dict. Like `...rest` in JavaScript.
</details>

---

**My score:** ___ / 11  ·  **Date:** ______  ·  **Retake score:** ___ / 11
