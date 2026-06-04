# Sample Agent-Run Autopsy

## Input

Goal:
Fix checkout route without changing auth, pricing, or database schema.

Redacted failure:

```text
Agent said the checkout bug was fixed, but no test was run.
Changed auth middleware while debugging a Stripe redirect.
Added a broad catch that returns success when createCheckoutSession fails.
The page now loads, but payment links silently fail in production.
Previous rollback note said not to touch auth for this route.
```

## Risk Score

85 - high regression risk.

## Likely Failure Modes

- The agent optimized for a passing-looking page load instead of the intended
  checkout behavior.
- The changed surface expanded from checkout into auth middleware.
- A broad catch created a success-shaped fallback that hides payment failures.
- The previous rollback boundary was not carried into the next run.
- No regression proof exists.

## Required Checks

- Add a failing regression test for checkout-session creation.
- Add a smoke check that proves payment-link creation fails loudly.
- Verify auth middleware did not change for unrelated routes.
- Confirm no schema, pricing, or database changes were made.

## Guardrail Prompt

```text
Goal: Fix checkout route without changing auth, pricing, schema, or unrelated
routes.

First: write or identify the failing regression check for checkout-session
creation.

Patch only the smallest primary path. Do not add broad catches or
success-shaped fallbacks. Payment/session errors must fail loudly.

Run the regression check and report the exact command output. Include rollback
notes for every changed file.
```
