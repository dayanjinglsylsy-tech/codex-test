---
name: automation-closure-operator
description: Finish or repair an existing automation without repeated rework. Use whenever Codex is asked to build, repair, activate, finish, close, or productionize an automation/workflow/integration under a limited work window, especially after repeated debugging cycles. Enforces Current-Reality-first, Upstream-First source pinning, reuse-before-build, read-only preflight, minimal real E2E, A/B/C/D blocker classification, double-run idempotency regression, quota protection, and short natural-language Founder handoff. Applies to n8n, APIs, webhooks, agents, scrapers, messaging, data pipelines, scheduled jobs, and similar automation work.
---

# Automation Closure Operator

Treat the job as a closure run, not an exploration run.

The objective is not “improve the system.” The objective is to reach a repeatable CORE DONE state with real readback and no known local rework tail.

## 1. Lock the outcome before touching anything

Restate the task in one short natural-language sentence:

`现有系统要从什么真实输入，稳定走到什么真实结果。`

Freeze scope. Do not add adjacent goals during the run.

If a company Current Reality / architecture authority exists, read it first. Preserve existing tree, owners, workflow IDs, databases, senders, consoles, agents, credentials, and Founder gates unless evidence proves a true gap.

Never create a second system merely because the first one is incomplete.

## 2. Upstream-First is mandatory

Before custom code or workflow mutation, identify the exact upstream owner for every node being touched.

Prefer, in order:

1. Official product Skill / README / docs / source code.
2. Maintainer-owned examples or reference implementations.
3. Mature open-source project documentation.
4. Existing local implementation already using that upstream method.
5. Custom code only for a confirmed true gap.

Do not rely on model memory when an authoritative upstream source exists.

For each proposed change, be able to answer in plain language:

`原厂已经怎么做？现有系统哪里偏离？这一刀只修什么？`

If this cannot be answered, do not mutate yet.

## 3. Read-only Preflight before mutation

Inspect the live/published/current state first:

- runtime/service health;
- active and reserve workflows;
- published graph/connections;
- credential references and auth health;
- webhook/callback registration;
- existing stores/tables/dedupe state;
- existing execution/readback evidence;
- side-effect boundaries.

Preflight must distinguish “service is alive” from “commercial E2E is proven.”

Do not rebuild capabilities already present.

## 4. Classify every blocker before fixing it

Every failure must be placed into exactly one class:

- **A — local workflow/code/config defect:** Codex may repair it.
- **B — credential/auth/Founder gate:** preserve working system and surface the one human action.
- **C — third-party API/rate limit/platform blocker:** preserve working system; do not redesign around a temporary external condition unless an approved upstream fallback already exists.
- **D — physical/business reality gate:** never “solve” it with code or fabricated state.

Only A permits continued repair work.

Do not reopen architecture to solve B/C/D.

## 5. Repair one evidenced defect at a time

Before each mutation, state:

`发现的具体 A 类故障是什么 → 为什么它阻止 CORE DONE → 最小修复是什么。`

Prefer native capabilities and existing components over new infrastructure.

A thin state table/store is allowed only when the workflow genuinely needs queryable lifecycle state, idempotency, callback correlation, TTL, or status branching. Do not let it become a second CRM/Lead DB/console.

No opportunistic refactors, naming cleanups, dashboard work, new agents, or “while we are here” improvements during closure.

## 6. First gate: minimal REAL E2E

Do not start with volume.

Run the smallest representative real path that proves the pipe:

`real input → qualification/logic → downstream side-effect preparation → readback`

Use real execution IDs, message IDs, draft IDs, callback IDs, rows, files, webhook responses, or equivalent proof for the system being tested.

Saved code, valid syntax, successful publish, or “theoretically works” is not E2E proof.

Do not trigger real irreversible SEND / SUBMIT / PUBLISH unless the Founder explicitly approved it.

If the first E2E exposes a local defect, fix that defect and rerun. Do not broaden the investigation.

## 7. Second gate: anti-rework regression

A first successful run is not CORE DONE.

Using the same published workflow, perform fresh readback and a second controlled run.

Prove all applicable conditions:

- same input does not duplicate irreversible or user-visible side effects;
- dedupe/idempotency behaves correctly;
- callback/message/job correlation does not cross-wire;
- callbacks are not consumed twice;
- published connections equal the intended graph after fresh readback;
- transient recoverable failures are absorbed by bounded retry;
- normal success stays quiet;
- real terminal failure reaches the intended error path;
- existing PASS branches remain unchanged.

Only after `first E2E PASS + second regression PASS + no duplicate side effects` may the run be marked **CORE DONE**.

## 8. Capacity proof comes after CORE DONE

Only after CORE DONE may Codex run a larger real batch or higher-volume test.

Capacity proof must never outrank correctness.

If external search, APIs, rate limits, scraping access, or slow upstreams reduce batch size, keep CORE DONE frozen and report the capacity limitation separately. Do not reopen architecture just to hit a count.

## 9. Protect the work-window quota

Use the work window in this order:

1. Current Reality + upstream source pinning.
2. Read-only Preflight.
3. Minimal real E2E.
4. Repair only evidenced A defects.
5. Second-run idempotency/regression.
6. Capacity proof only with remaining time.

If more than half the available window is consumed and minimal E2E is still not reached, stop broad research immediately. Identify the single current blocker, classify A/B/C/D, and concentrate only on the shortest path to the E2E gate.

Never spend the final portion of the quota collecting more candidates, polishing logs, rewriting documentation, or expanding the system while regression remains unproven.

## 10. Founder communication must stay natural-language short

Do not send raw logs, code stacks, giant audit tables, long prompts, or internal implementation narration unless explicitly requested.

During work, report only when something materially changes the next action:

`现在是什么 → 真正问题是什么 → 下一步做什么。`

Final handoff must answer only:

- 现在真正跑通了什么；
- CORE DONE 是否经过双跑；
- 真实产出了什么；
- 是否还有阻止反复运行的问题；
- 若有，它属于 A/B/C/D 哪类；
- Founder 现在唯一需要做什么。

## CORE DONE definition

CORE DONE requires all applicable evidence below:

- live/current/published graph readback;
- representative real execution evidence;
- real downstream readback;
- first E2E PASS;
- second controlled regression PASS;
- no duplicate side effects;
- correct failure boundary;
- no unresolved A-class defect known to block repeat operation.

B/C/D blockers may remain OPEN without invalidating already-proven local CORE DONE, but they must be stated truthfully and must not be disguised as code work.

## STOP conditions

Stop and do not widen scope when:

- the requested outcome is already proven;
- the remaining blocker is B, C, or D;
- a proposed new system duplicates an existing owner;
- an upstream source already provides the needed capability;
- the next action would consume quota without improving CORE DONE evidence.

The closure run is successful when the Founder can use the automation again without returning to repair the same local defect class.