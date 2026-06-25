# Code Review Example

## Prompt

```text
Use $meta-debug-pbl to review this function. Prioritize bugs and explain the lesson learned.
```

## Expected Response Shape

```md
## Findings

- High: `src/cart.ts:42` allows negative quantities, which can reduce the total below zero.
  Fix by validating `quantity > 0` before updating the cart.

- Medium: `src/cart.ts:58` does not handle missing products.
  Return a typed error or skip the update with a clear message.

## Verification

Add tests for negative quantity, missing product, and normal quantity updates.

## Learning Note

Validation belongs at the boundary where unsafe input enters the system.
```
