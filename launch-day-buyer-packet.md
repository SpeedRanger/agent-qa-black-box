# Launch-Day Buyer Packet

> Product: Agent QA Black Box
> Offer: `$19` public/redacted agent-run autopsy
> Live app: https://speedranger.github.io/agent-qa-black-box/
> Reserve: https://speedranger.github.io/agent-qa-black-box/reserve-slot.md

## The Buyer Problem

AI coding agents increasingly produce useful code, but the painful paid problem
is the review gap after a run:

- the agent says "done" without proof
- the diff touches unrelated surfaces
- broad catches hide the real failure
- tests are missing or fake
- the next agent repeats the same mistake

Agent QA Black Box turns one failed public/redacted run into a prevention packet
that a builder can hand back to Codex, Claude Code, Cursor, or a human reviewer.

## What The `$19` Autopsy Delivers

For one public/redacted failed run:

1. likely failure modes
2. missing regression checks
3. guardrails for the next agent run
4. rollback note
5. copy-ready next prompt

Launch-sprint accepted slots target delivery within `24 hours` after payment
evidence and scope-fit confirmation.

## Example Input

```text
Goal: Fix checkout route without changing auth, pricing, or database schema.

Agent said the checkout bug was fixed, but no test was run.
Changed auth middleware while debugging a Stripe redirect.
Added a broad catch that returns success when createCheckoutSession fails.
The page now loads, but payment links silently fail in production.
Previous rollback note said not to touch auth for this route.
```

## Example Output

```md
Risk score: 85 - high regression risk.

Likely failure modes:
- The agent optimized for a passing-looking page load instead of checkout.
- The changed surface expanded from checkout into auth middleware.
- A broad catch created a success-shaped fallback that hides payment failures.
- The previous rollback boundary was not carried into the next run.

Required checks:
- Add a failing regression test for checkout-session creation.
- Add a smoke check that proves payment-link creation fails loudly.
- Verify auth middleware did not change for unrelated routes.
- Confirm no schema, pricing, or database changes were made.

Next prompt:
Fix checkout route without changing auth, pricing, schema, or unrelated routes.
First write or identify the failing regression check for checkout-session
creation. Patch only the smallest primary path. Payment/session errors must fail
loudly. Run the regression check and report exact command output.
```

## Reserve A Slot

Open the public-safe request form:
https://github.com/SpeedRanger/agent-qa-black-box/issues/new?template=agent_run_autopsy.yml

The form now asks for:

- public context URL
- intended outcome
- redacted run/failure/diff summary
- optional generated packet
- payment handoff preference
- delivery window
- public-safety confirmation

## Payment And Proof Boundary

Do not include payment details in a public issue.

Revenue is counted only when receipt/export/invoice or buyer-confirmed payment
evidence exists. Public comments, interest, and unpaid reservations do not count
as revenue.

## Public-Safety Boundary

Do not include:

- secrets
- tokens
- private repos
- private logs
- private analytics
- customer data
- payment details
- NDA material
