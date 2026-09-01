# Completion Contract

Load this file only when the task reaches final verification/handoff, or when the user explicitly asks for all/complete/100%/fully unattended operation.

## Scope reconciliation

Before using the word DONE, reconcile the user-requested Scope Manifest line by line.

Each in-scope line must be exactly one of:
- `PASS — fresh evidence attached`
- `BLOCKED — exact blocker and class`
- `NOT TESTED — therefore not done`

No silent scope narrowing. A working core path does not make omitted requested branches complete.

## Evidence

Use fresh evidence appropriate to each branch, for example:
- execution/run ID;
- message/draft/release/post ID;
- callback or stored-state readback;
- public URL;
- published workflow/version readback;
- explicit zero-result reason;
- retry/error-path result.

Installed/configured/saved/healthy is not equivalent to a completed real branch.

## Full completion

When the user asked for all / complete / 100% / fully unattended operation, `FULL DONE = YES` only when every applicable requested branch is PASS.

Typical requirements when applicable:
- current published graph/version readback;
- all Scope Manifest branches PASS;
- representative real E2E PASS;
- real downstream readback;
- no unresolved in-scope blocker;
- repeatability proof;
- schedule-trigger proof for unattended scheduled operation.

Anything less is `FULL DONE = NO`.

## Repeatability

For repeatable automations, perform a second controlled regression without creating duplicate irreversible/public side effects. Verify applicable conditions:
- dedupe/idempotency works;
- no cross-brand/cross-item/callback cross-wire;
- prior run is not overwritten;
- callbacks are not consumed twice;
- recoverable failures use bounded retry;
- terminal failures surface explicitly;
- valid zero-result states are explicit;
- previously PASS branches remain intact.

## Scheduled operation

If unattended scheduling is part of the requested outcome, manual E2E alone is insufficient. Require a fresh real schedule/production-trigger execution on the same published version with downstream readback.

A trigger that wakes successfully but produces an invalid/ambiguous business result is not a schedule PASS.

## Side-effect guard

Do not trigger irreversible SEND / SUBMIT / PUBLISH / PAYMENT / destructive mutation unless current Authority or explicit user approval permits it.
