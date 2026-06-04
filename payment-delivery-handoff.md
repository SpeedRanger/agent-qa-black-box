# Payment And Delivery Handoff

> Product: Agent QA Black Box
> Offer: `$19` public/redacted agent-run autopsy
> Public request form: https://github.com/SpeedRanger/agent-qa-black-box/issues/new?template=agent_run_autopsy.yml

## Buyer Flow

1. Buyer opens the public request form.
2. Buyer provides only:
   - intended outcome
   - public context URL, if available
   - redacted agent run, failure, or diff summary
   - generated Agent QA packet, if available
3. Seller confirms the request is public-safe and scope-fit.
4. Seller and buyer move payment and private delivery to a buyer-approved
   private channel.
5. Seller delivers:
   - likely failure modes
   - required regression checks
   - guardrails for the next agent run
   - rollback note
   - next prompt
6. Revenue is counted only after receipt/export/invoice evidence exists.

## What Counts As Paid

Count revenue only when one of these exists:

- paid invoice reference
- checkout/payment export
- receipt reference
- other buyer-confirmed payment record

Do not count:

- public issue interest
- comment intent
- a claimed slot without payment evidence
- private messages without receipt/export/invoice evidence

## Scope Boundary

Included:

- one public/redacted agent run
- one intended outcome
- one autopsy packet
- one next prompt

Not included:

- guaranteed bug fix
- private repo review
- private log review
- secrets handling
- customer-data handling
- ongoing engineering support
- guaranteed Product Hunt ranking
