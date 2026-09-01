---
name: automation-closure-operator
description: Thin completion-contract wrapper for existing automations. Use when the user asks to finish, repair, close, productionize, validate end-to-end, or make an existing automation repeatable—especially when they require all/complete/100% results or a bounded work window. This skill does not replace Superpowers or product-specific official skills; it only owns full-scope reconciliation, truthful completion semantics, and quota discipline.
---

# Automation Closure Operator

Use this as a **thin closure layer**, not as a debugging framework, workflow engine, or replacement for upstream documentation.

## Authority order

Always follow this order:
1. Current user/company Authority and Current Reality.
2. Exact official/upstream Skill, README, docs, or source for the software being touched.
3. Superpowers for debugging, TDD where applicable, and verification-before-completion.
4. This skill for scope/completion reconciliation only.

If technical instructions conflict, upstream technical instructions win. This skill owns only the user's requested scope, definition of DONE, and bounded-work discipline.

## Fast path

### 1. Lock the requested outcome

Restate the user's actual end state in one sentence, then build a **Scope Manifest** containing every requested branch.

Do not silently narrow “全部 / 完整 / 100%” into a convenient core path.

### 2. Read the smallest Current sources

Read Current Authority/Reality first. Use exact pointers and targeted retrieval; do not scan whole Drives, repositories, archives, chats, or historical handoffs “just in case.”

Historical material is evidence only unless Current Authority explicitly promotes it.

### 3. Preserve the existing architecture

Reuse current workflow IDs, owners, databases, credentials, senders, consoles, publishers, and gates unless evidence proves a true gap.

Do not create a second CRM, DB, agent framework, publisher, radar, console, or orchestration layer merely because an existing branch is incomplete.

Do not reopen a proven PASS branch without regression evidence.

### 4. Upstream-first before mutation

For every node being changed, identify its exact upstream owner and answer:

`原厂怎么做 → 当前实现哪里偏离 → 这一刀只修什么。`

Prefer official product Skill/docs/source, maintainer examples, and the existing local implementation before custom code.

### 5. Read-only preflight, then smallest real E2E

Before mutation, inspect only what is required to know:
- current/published workflow or graph;
- credential/auth references and health;
- recent execution/readback evidence;
- dedupe/state boundaries;
- side-effect gates;
- Scope Manifest branches.

Distinguish installed/configured, service-alive, branch-PASS, and full requested E2E. They are not interchangeable.

Run the smallest representative real E2E as early as safely possible. Do not spend the work window polishing architecture before learning where Reality actually breaks.

### 6. Debug only evidenced defects

For bugs, unexpected behavior, empty-success runs, broken callbacks, routing defects, or regressions, use Superpowers `systematic-debugging`; use TDD when applicable and `verification-before-completion` before success claims.

Fix the root cause with the minimum change. No opportunistic refactors or unrelated upgrades.

### 7. Treat external gates as gates, not coding invitations

If auth, OAuth, Cookie, QR, CAPTCHA, platform review, third-party outage, GPU/API queue, physical Reality, or another human/external dependency blocks a branch without evidence of a local defect, stop modifying already-valid code for that branch.

When a blocker actually appears, load `references/bounded-work-and-blockers.md` for classification and quota rules.

### 8. Final verification is scope-wide

A successful execution is not automatically full completion. Before the word DONE, reconcile every Scope Manifest branch with fresh evidence.

At final verification/handoff—or whenever the user explicitly requires all/complete/100%/fully unattended operation—load `references/completion-contract.md` and apply it.

### 9. Bounded work windows

Never promise certainty that current evidence cannot support. If an external/unknown dependency can still block the full requested result, say so literally.

When the user gives a fixed engineering window/quota, load `references/bounded-work-and-blockers.md` only when needed for feasibility, blocker handling, or time-budget decisions.

## Founder/user communication

Keep operational handoff short. Report:
- `FULL DONE = YES / NO` when the user requested full completion;
- which requested branches PASS;
- which do not;
- the fresh evidence identifiers for PASS branches;
- the exact blocker/action for non-PASS branches;
- the single user action, if any.

Do not dump giant logs unless requested.

## Non-negotiable completion semantics

- No partial completion masquerading as full completion.
- No unsupported “100%”.
- No hidden scope narrowing.
- No duplicate system to avoid repairing the current one.
- No coding around a real external/human gate.
- No DONE claim without fresh verification.

## Delete-this-skill test

Keep this skill only while it adds a user-level contract not already owned by upstream tools: full requested-scope reconciliation, truthful full-vs-partial completion semantics, and bounded-work discipline.

If upstream skills provide those guarantees together, delete this wrapper instead of duplicating them.
