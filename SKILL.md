---
name: code-craft
description: Engineering discipline for writing and reviewing code. Evidence hierarchy, minimal intrusion, adversarial self-review, and four-part delivery. Use before making changes or reviewing PRs.
---

# Code Craft

Principles to run through before writing or reviewing code.

## Work Chain

Scoping → Evidence Verification → Call-Chain Tracing → Convention Check → Minimal Change → Adversarial Self-Review → Real Verification → Handoff

## Eight Principles

1. **Pick clean-boundary tasks first** — Compare dependencies, decision authority, and verification cost. Do what can be done independently.

2. **Evidence has a hierarchy** — Live DB schema > actual call chain > current code > comments > documentation. Trust what actually runs.

3. **Code exists ≠ it's alive** — Commented-out code and uncalled methods are not existing capabilities. Don't treat them as "hooking into an existing flow."

4. **Know the conventions before touching** — Routing, auth, error handling, code style. Match the project, don't invent.

5. **Minimum viable intrusion** — Bonus features failing must not crash core business. Local failure → local degradation only.

6. **Adversarial self-review after writing** — Privilege escalation, cross-tenant access, parameter mixing, missing params, unauthenticated paths, exception dependencies. Go through every one.

7. **Compiles ≠ correct** — Real auth, real database, positive and negative scenarios. All must pass.

8. **Keep the correction trail** — Record "original judgment → new evidence → why the change." Don't hide mistakes.

## Code Style

- Follow the project's existing patterns. Don't introduce alien conventions.
- Reuse proven patterns. Don't create abstractions speculatively.
- Decouple core flow from bonus information. Bonus failure → graceful degradation only.
- Read-only ≠ anyone can read. Always check data ownership.
- Legacy systems: understand WHY before judging whether it still applies.

## Delivery: Four-Part Format

When presenting code changes:

1. **Thought Process** — What was observed, how it was judged
2. **Before → After** — Per-file diff with line numbers
3. **Why** — Style choices and trade-off rationale
4. **Verification** — Scenario matrix, positive/negative cases, known gaps

## Usage

Invoke this skill when:
- Starting a code change (run through the eight principles first)
- Reviewing a PR or a diff
- Debugging why a previous change introduced a regression
- Onboarding to a new codebase (convention-check before touching)
- Writing a handoff document for the next person
