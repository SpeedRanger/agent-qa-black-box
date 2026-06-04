# Buyer Outreach Packet

Use this only for public-safe outreach. Do not ask for private repos, private
logs, secrets, customer data, private analytics, or payment details in public.

## Buyer Targets

- Developers using Codex, Claude Code, Cursor, or similar coding agents.
- Founders debugging vibe-coded apps.
- Teams reviewing AI-generated diffs.
- Tool builders whose users complain about flaky AI-generated code.
- Public GitHub issue threads where an agent-made fix regressed behavior.

## Good Fit

- Failed agent run can be described from public/redacted text.
- There is a clear intended outcome.
- There is missing verification or broad/fallback behavior.
- Buyer wants a prevention packet before running the next fix attempt.

## Bad Fit

- Requires private repo access.
- Requires secrets, private logs, customer data, or NDA material.
- Buyer only wants someone to implement the whole fix immediately.
- No public or redacted failure description exists.

## Public Comment Template

```text
This looks like an agent-run QA problem more than a prompt problem.

The missing artifact is the regression pack: what changed outside the target
surface, what check would have caught it, what the next agent must not touch,
and what command proves the fix.

I built Agent QA Black Box for exactly that:
https://speedranger.github.io/agent-qa-black-box/

Public/redacted inputs only. No secrets, private repos, private logs, customer
data, or payment details.
```

## Paid Slot Reply

```text
I can do a $19 public/redacted agent-run autopsy for this.

Open the public request form with the intended outcome and the redacted run:
https://github.com/SpeedRanger/agent-qa-black-box/issues/new?template=agent_run_autopsy.yml

If the request is public-safe and scope-fit, payment and delivery can move to a
buyer-approved private channel. Revenue is counted only after receipt/export/
invoice evidence exists.
```
