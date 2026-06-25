# Debugging Example

## Prompt

```text
Use $meta-debug-pbl to debug this error and explain it like a programming mentor:

TypeError: cannot read properties of undefined (reading 'map')

The error happens in a React component that renders `items.map(...)`.
```

## Expected Response Shape

```md
## Diagnosis

The component is calling `.map()` before `items` has a usable array value.

## Fix

Initialize `items` as an empty array, guard the render path, or normalize the API response before rendering.

## Verify

Reload the component with loading, empty, and populated states.

## What Was Happening

`.map()` is an array method. If `items` is `undefined`, JavaScript cannot call array methods on it.

## Learning Note

Async UI often renders once before data arrives. Give the first render a safe default value.
```
