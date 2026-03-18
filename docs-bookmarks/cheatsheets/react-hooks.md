# React hooks patterns

## useEffect mental model
- Sync with external systems (network, subscriptions, timers).
- Avoid using it for "derived state" (compute during render instead).

## Common patterns

### Fetch with abort
```ts
useEffect(() => {
  const controller = new AbortController();

  (async () => {
    const res = await fetch("/api/items", { signal: controller.signal });
    if (!res.ok) throw new Error("Request failed");
    // setState(await res.json());
  })().catch(err => {
    if (err.name !== "AbortError") console.error(err);
  });

  return () => controller.abort();
}, []);
```

### Stable callbacks
- Prefer `useCallback` when passing handlers into memoized children or deps arrays.
- Prefer `useMemo` for expensive computations or stable object/array identities.

### Derived state
Avoid:
```ts
const [fullName, setFullName] = useState("");
useEffect(() => setFullName(first + " " + last), [first, last]);
```
Prefer:
```ts
const fullName = `${first} ${last}`;
```
