# Agent QA Black Box

Agent QA Black Box turns a failed AI coding/session run into a concrete
regression pack: likely failure modes, required checks, guardrails, rollback
notes, and the next prompt.

Live target:

- Site: https://speedranger.github.io/agent-qa-black-box/
- Repo: https://github.com/SpeedRanger/agent-qa-black-box
- Public request form: https://github.com/SpeedRanger/agent-qa-black-box/issues/new?template=agent_run_autopsy.yml
- Public launch issue: https://github.com/SpeedRanger/agent-qa-black-box/issues/1

## Why this exists

AI coding agents are getting more capable, but the painful failure mode is not
"the agent made a mistake." It is when a run looks complete, changes the wrong
surface, skips verification, hides failure with broad fallback logic, and leaves
the same bug ready to return.

Agent QA Black Box is not another coding agent. It is the proof layer after an
agent run: what failed, what must be tested, what must not be changed, and how
to hand the next attempt to Codex, Claude Code, Cursor, or a human reviewer.

## Public product

- `index.html` - static first-use app
- `.github/ISSUE_TEMPLATE/agent_run_autopsy.yml` - public-safe request form
- `sample-agent-autopsy.md` - example output
- `product-hunt-launch-assets.md` - Product Hunt launch copy and replies
- `buyer-outreach-packet.md` - public-safe outreach copy
- `payment-delivery-handoff.md` - paid request and evidence rules
- `launch-status.json` - public launch and proof gates
- `launch-ledger.md` - launch state and revenue slots
- `llms.txt` - machine-readable summary
- `AGENTS.md` - product-specific agent instructions

## Paid wedge

The first 24h paid product is a `$19` agent-run autopsy for one public or
redacted failed agent run. One paid autopsy clears the `$10` target before fees
only when receipt/export/invoice evidence exists.

The buyer sends a public/redacted run and receives:

- likely failure modes
- required regression checks
- guardrails for the next agent run
- rollback note
- next prompt

Do not collect secrets, private repo access, private logs, private analytics,
customer data, payment details, or private strategy in public issues.

## Run locally

Open `index.html` directly or serve the folder:

```powershell
python -m http.server 4192 -d ui/agent-qa-black-box
```

Then open `http://localhost:4192`.

## Hard limits

Agent QA Black Box does not guarantee Product Hunt placement, bug fixes, AI
agent correctness, or revenue. It creates a concrete autopsy and prevention
packet from public/redacted inputs.
