# Week 6 · Quiz: React intermediate

**Mon Nov 16 – Sun Nov 22, 2026**

[← Back to roadmap](../../README.md) · [Plan](plan.md) · [Quiz](quiz.md) · [Interview prep](interview-prep.md)

> Answer **in your head or on paper first**, then open the answer. No AI, no Google. ✍️ = write code by hand.

**Q1.** `useMemo` vs `useCallback`?
<details><summary>Answer</summary>

`useMemo` caches a **value**. `useCallback` caches a **function** reference. Use them for expensive calculations, or to keep references stable for memoized children or effect dependencies.
</details>

**Q2.** ✍️ Write a custom hook `useLocalStorage(key, initial)`.
<details><summary>Answer</summary>

```ts
function useLocalStorage<T>(key: string, initial: T) {
  const [value, setValue] = useState<T>(() => {
    const saved = localStorage.getItem(key);
    return saved ? JSON.parse(saved) : initial;
  });
  useEffect(() => {
    localStorage.setItem(key, JSON.stringify(value));
  }, [key, value]);
  return [value, setValue] as const;
}
```
</details>

**Q3.** When is `useReducer` better than `useState`?
<details><summary>Answer</summary>

When the state is complex (several related values) or the next state depends on many kinds of actions. It keeps update logic in one testable place.
</details>

**Q4.** When does a React component re-render?
<details><summary>Answer</summary>

When its state changes, when its parent re-renders (even if the props are the same, unless it's wrapped in `React.memo`), or when a context it uses changes.
</details>

**Q5.** Does changing a `useRef` value cause a re-render?
<details><summary>Answer</summary>

No. `ref.current` is a mutable box that survives renders without triggering one. That's why it's good for timers, previous values and DOM nodes.
</details>

**Q6.** Context vs a state library (Redux/Zustand): when do you use each?
<details><summary>Answer</summary>

Context is fine for rarely changing global values (theme, current user). For large, frequently updated state, a library avoids re-rendering every consumer and gives you devtools and structure.
</details>

## 🐍 Python track

**Q7.** Generator vs list: what's the difference, and when does it matter?
<details><summary>Answer</summary>

A list stores every item in memory. A generator produces items one at a time with `yield`, only when asked. Use a generator for big or infinite data (for example, reading a huge file line by line).
</details>

**Q8.** ✍️ Return the 2 most common words in `words` (a list of strings).
<details><summary>Answer</summary>

```python
from collections import Counter

top_two = Counter(words).most_common(2)
```
</details>

**Q9.** What does a `with` statement guarantee?
<details><summary>Answer</summary>

The resource's cleanup (`__exit__`) always runs, even if an exception happens. For example, a file is always closed.
</details>

---

**My score:** ___ / 9  ·  **Date:** ______  ·  **Retake score:** ___ / 9
