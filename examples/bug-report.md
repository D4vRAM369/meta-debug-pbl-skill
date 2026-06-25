# Bug Report Example

````md
# BUG-map-undefined: React list crashed before data loaded

## Context

A React component rendered `items.map(...)` while waiting for API data.

## Symptom

The page crashed with `TypeError: cannot read properties of undefined`.

## Expected Behavior

The page should show a loading or empty state until the item list is available.

## Root Cause

The first render used `items` before it had been initialized as an array.

## Fix Applied

Initialize state with an empty array and keep the render path safe.

## Before

```tsx
const [items, setItems] = useState();
```

## After

```tsx
const [items, setItems] = useState<Item[]>([]);
```

## Verification

Checked loading, empty, and populated list states.

## Lesson Learned

Async data may not exist during the first render. Components should render safely before data arrives.

## Prevention

Use typed default state and add tests for loading and empty states.
````
