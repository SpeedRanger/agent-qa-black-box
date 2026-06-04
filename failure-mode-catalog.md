# Agent Failure Mode Catalog

> Product: Agent QA Black Box
> Use: public-safe buyer proof and launch positioning

Agent QA Black Box is built around repeated failure modes seen in current AI
coding-agent discussions and launch research. This catalog is not a claim that
the product has fixed a customer's repo. It is the taxonomy the `$19`
public/redacted autopsy service uses to turn one failed run into a prevention
packet.

## What The Autopsy Looks For

### 1. Proofless Done

The agent reports success without a command, test, screenshot, or other
verifiable artifact.

Autopsy output:

- required regression check
- exact proof command to rerun
- done-condition rewrite
- next prompt that forbids success-shaped summaries

### 2. Surface Drift

The task targets one route, component, or bug, but the agent changes adjacent
auth, pricing, schema, routing, styling, or state code.

Autopsy output:

- blast-radius note
- files to quarantine from the next run
- rollback note
- narrow patch boundary

### 3. Success-Shaped Fallback

The agent hides the real failure behind a broad catch, silent default, fake
success response, mocked dependency, or happy-path-only UI state.

Autopsy output:

- fail-loud rule
- missing negative test
- fallback deletion target
- production-like smoke check

### 4. Repeated Scar

The agent repeats a bug, migration, dependency choice, or architectural pattern
that the team already reverted.

Autopsy output:

- scar-tissue rule
- prompt constraint for future sessions
- memory/doc update
- guardrail check

### 5. Context Waste Loop

The agent burns tool calls reading broad files, repeating failed commands, or
summarizing context instead of shrinking the problem.

Autopsy output:

- task boundary
- smallest useful file set
- stop condition
- handoff summary for a fresh run

### 6. Fake Test Confidence

The agent adds tests that do not exercise the real behavior, mocks the thing
under test, or leaves empty assertions.

Autopsy output:

- mutation-style challenge
- test realism check
- required failing test before patch
- proof command and expected failure/success signal

## Autopsy Packet Template

```md
## Agent QA Black Box

Risk score: <0-100>

### Likely failure modes
- <failure mode>

### Required checks
- <specific test, smoke check, or screenshot proof>

### Guardrails for next run
- <what the next agent must not touch>

### Rollback note
- <what to undo if the next run expands scope>

### Next prompt
<copy-ready prompt for the next agent run>
```

## Public-Safety Boundary

Use public or redacted inputs only. Do not put secrets, tokens, private repos,
private logs, private analytics, customer data, payment details, or NDA material
in public issues.

## Paid Slot

Request a `$19` public-safe autopsy slot:
https://github.com/SpeedRanger/agent-qa-black-box/issues/new?template=agent_run_autopsy.yml
