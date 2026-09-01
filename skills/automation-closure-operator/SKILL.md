---
name: automation-closure-operator
description: Thin completion-contract wrapper for existing automations. Use only when the user asks to finish, repair, close, productionize, or make an existing automation fully repeatable under a bounded work window. This skill does NOT replace Superpowers or the current software's official skills. It adds only three user-level guarantees that upstream technical skills do not own: full-scope reconciliation, no partial-completion masquerading as done, and truthful feasibility/completion reporting.
---

# Automation Closure Operator

This is a THIN wrapper, not a debugging framework and not a substitute for upstream skills.

Always use, in this order:
1. Current company Authority / Reality.
2. Superpowers for root-cause debugging, TDD where applicable, and verification-before-completion.
3. The current software's official Skill / README / docs / source.
4. This skill only to enforce the user's completion contract across the whole requested scope.

If this skill conflicts with Superpowers or an official software skill on technical implementation, the upstream technical skill wins. This skill only owns scope, completion semantics, and bounded-work discipline.

## 0. Never promise certainty you cannot prove

Before mutation, give a feasibility verdict for the USER'S FULL REQUEST, not for a convenient subset.

Allowed verdicts:
- `FULL COMPLETION GUARANTEED BY CURRENT EVIDENCE` — use only when every required dependency is already available, every required credential/auth/physical gate is known satisfied, and the remaining work is deterministic and locally controllable.
- `FULL COMPLETION NOT GUARANTEED YET` — required whenever any unknown runtime behavior, external API/platform state, missing credential/auth, human approval, physical dependency, or unverified branch can still block the full outcome.

Never translate “high probability” into “guaranteed.”
Never say “100%” unless current evidence genuinely proves that no unresolved external or unknown dependency can prevent completion.

If the user asks “can this definitely be finished in N hours?” and certainty cannot be proven, answer NO and identify exactly what additional condition, access, or reserve capacity removes the uncertainty. Do not soften this into optimistic percentages.

## 1. Lock the FULL requested outcome before touching anything

Restate the user's requested end state in one sentence:

`现有系统要从什么真实输入，稳定走到哪些真实结果，全部哪些分支都必须成立。`

Then build a SCOPE MANIFEST from current Authority / Reality before mutation.

The manifest must enumerate every in-scope branch that the user asked to be finished. Example categories:
- triggers / schedules;
- discovery / search;
- qualification / scoring;
- routing;
- Gmail draft or other output;
- Telegram/mobile approval controls;
- WhatsApp or other requested contact rail;
- dedupe / idempotency;
- error handling / retries / explicit zero-result state;
- published/live schedule proof.

No silent scope narrowing.
No declaring the job done because one path works.
No replacing “全部” with “core path” unless the user explicitly agrees.

## 2. Preserve the current architecture

Read current Authority / Reality first.
Preserve existing tree, owners, workflow IDs, databases, senders, consoles, agents, credentials, and Founder gates unless evidence proves a real gap.

Never create a second system merely because the first one is incomplete.
Never reopen already-proven PASS branches without evidence they regressed.

## 3. Upstream-First is mandatory

Before custom code or workflow mutation, identify the exact upstream owner for every node being touched.

Prefer, in order:
1. Official product Skill / README / docs / source code.
2. Maintainer-owned examples or reference implementations.
3. Mature open-source project documentation.
4. Existing local implementation already using that upstream method.
5. Custom code only for a confirmed true gap.

For every proposed change, be able to answer:
`原厂已经怎么做？现有系统哪里偏离？这一刀只修什么？`

If this cannot be answered, do not mutate yet.

## 4. Read-only preflight before mutation

Inspect the live/published/current state first:
- runtime/service health;
- active and reserve workflows;
- published graph/connections;
- credential references and auth health;
- webhook/callback registration;
- stores/tables/dedupe state;
- recent execution/readback evidence;
- side-effect boundaries;
- every branch in the Scope Manifest.

Preflight must distinguish:
- installed/configured;
- service alive;
- one branch previously passed;
- FULL requested commercial E2E currently proven.

These are not interchangeable.

## 5. Use Superpowers for debugging — do not duplicate it here

For bugs, unexpected behavior, empty-success runs, broken callbacks, routing defects, or regressions:
- invoke Superpowers `systematic-debugging`;
- find root cause before fixes;
- compare working vs broken evidence;
- test one hypothesis at a time;
- use TDD when applicable;
- use `verification-before-completion` before any success claim.

After 3 failed minimal fixes to the same defect, STOP. Do not attempt a fourth guess. Re-open root-cause investigation and, if required by Superpowers, question the architecture with the user.

This skill must never weaken or bypass those rules.

## 6. Classify blockers, but do not call blocked scope DONE

Classify every blocker:
- A — local workflow/code/config defect: Codex may repair.
- B — credential/auth/Founder gate.
- C — third-party API/rate limit/platform blocker.
- D — physical/business reality gate.

Important completion rule:
- A/B/C/D are useful for deciding WHAT TO DO NEXT.
- They do NOT permit a blocked in-scope branch to be called done.

If any requested in-scope branch remains blocked by A, B, C, or D:
`FULL DONE = NO`.

You may separately say which local branches are proven, but never relabel partial/local completion as CORE DONE when the user's request was “全部 / 完整 / 100%”.

## 7. Repair only evidenced defects

Before each mutation state internally:
`具体故障是什么 → 为什么阻止某个 Scope Manifest 分支 → 最小修复是什么。`

Prefer native capabilities and existing components.
No opportunistic refactors, naming cleanups, dashboards, new agents, second CRM/Lead DB/console, or unrelated expansion during closure.

## 8. Verification is per branch, then end-to-end

A single successful execution is never enough for a full-scope request.

For every Scope Manifest branch, obtain fresh evidence appropriate to that branch, such as:
- execution ID;
- message ID;
- draft ID;
- callback readback;
- stored row/state;
- actual URL;
- published workflow/version readback;
- explicit zero-result reason;
- retry/error-path evidence.

Then run the smallest representative REAL E2E that crosses the requested system from true input to true user-visible output.

Do not trigger irreversible SEND / SUBMIT / PUBLISH unless the user explicitly approved it.

## 9. Mandatory second regression for repeatable automations

For repeatable/scheduled automations, FULL DONE also requires a second controlled run on the same published workflow and fresh readback proving all applicable conditions:
- no duplicate irreversible/user-visible side effects;
- dedupe/idempotency correct;
- no cross-brand/cross-item/callback cross-wire;
- callbacks not consumed twice;
- published connections still match intended graph;
- recoverable failures handled by bounded retry;
- terminal failures surface explicitly;
- explicit zero-result states do not masquerade as generic Success;
- previously PASS branches remain intact.

## 10. If the user requested unattended scheduling, schedule proof is mandatory

Manual E2E + regression is insufficient when the user's requested outcome is unattended scheduled operation.

FULL DONE additionally requires at least one fresh REAL Schedule Trigger / production-trigger execution on the same published version, with downstream readback.

If the schedule merely wakes but business output is wrong/empty without an explicit valid zero-result terminal state, FULL DONE = NO.

## 11. Full completion matrix is mandatory before the word DONE

Before final handoff, reconcile the Scope Manifest line by line.

Each line must be exactly one of:
- `PASS — fresh evidence attached`
- `BLOCKED — exact blocker and class A/B/C/D`
- `NOT TESTED — therefore not done`

FULL DONE may be YES only if every in-scope line is PASS.

There is no percentage-based shortcut.
There is no “mostly done.”
There is no “core done” substitute for a user's explicit full-scope request.

## 12. Bounded work-window / quota rule

Use the work window in this order:
1. Scope Manifest + Current Reality + upstream source pinning.
2. Read-only preflight.
3. Root-cause work via Superpowers for the first failing branch.
4. Minimal repair of evidenced A defects.
5. Per-branch fresh verification.
6. Real E2E.
7. Second regression.
8. Real schedule-trigger proof if requested.
9. Only then capacity/volume testing.

If a B/C/D blocker appears, stop burning engineering quota on that blocker and surface the exact human/external action. Preserve already-proven branches.

If the work window ends before every in-scope branch passes, report `FULL DONE = NO`. Never use quota exhaustion as a reason to downgrade the user's requested definition of done.

## 13. Founder communication stays short and literal

Do not send giant logs unless requested.
Final handoff for a full-scope request must answer only:
- FULL DONE = YES / NO;
- Scope Manifest branches that PASS;
- any branch not PASS;
- exact evidence IDs for each PASS branch;
- exact blocker class/action for each non-PASS branch;
- whether a real scheduled production trigger passed when required;
- whether any unresolved A-class defect remains;
- the single Founder action, if any.

## FULL DONE definition

When the user asked for all / complete / 100% / fully unattended operation:

FULL DONE = YES only when ALL applicable requested branches have fresh evidence and all required repeatability/schedule gates pass.

Required when applicable:
- live/current/published graph readback;
- all Scope Manifest branches PASS;
- representative real E2E PASS;
- real downstream readback;
- second controlled regression PASS;
- no duplicate side effects;
- correct explicit zero-result/error boundary;
- no unresolved A/B/C/D blocker on any requested in-scope branch;
- real production Schedule Trigger PASS for unattended scheduled workflows.

Anything less is FULL DONE = NO.

## Delete-this-skill test

This skill should remain only because it adds a thin user-level completion contract not owned by Superpowers or product-specific official skills.

If future upstream skills natively provide all of the following together:
1. full user-scope manifest/reconciliation;
2. explicit prohibition on partial completion masquerading as full completion;
3. truthful guaranteed-vs-not-guaranteed feasibility semantics for bounded work windows;
4. mandatory per-branch + E2E + repeatability + schedule completion matrix;

then this file has no unique job and SHOULD BE DELETED rather than duplicated.
