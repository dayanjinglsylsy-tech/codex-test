# Bounded Work and Blockers

Load this file only when a bounded work window/quota is material, or when a blocker actually appears.

## Feasibility language

Never promise certainty that current evidence cannot support.

Use:
- `FULL COMPLETION GUARANTEED BY CURRENT EVIDENCE` only when every required dependency/auth/human/physical gate is already proven available and the remaining work is deterministic and locally controllable.
- `FULL COMPLETION NOT GUARANTEED YET` whenever unknown runtime behavior, external API/platform state, missing auth, human approval, physical dependency, or an unverified branch can still block the full outcome.

Do not convert “likely” into “100%”.

## Blocker classes

Classify the actual blocker, not hypothetical future gates:
- `A` — local workflow/code/config defect; repairable by Codex.
- `B` — credential/auth/Founder-only action.
- `C` — third-party API/rate-limit/platform/outage/queue blocker.
- `D` — physical/business Reality gate.

A/B/C/D guide the next action. They do not make a blocked requested branch DONE.

## Quota discipline

Use bounded engineering time in this order:
1. lock requested scope and current Reality;
2. read-only preflight;
3. pin exact upstream owner for touched nodes;
4. run the smallest real E2E;
5. repair only evidenced A-class defects using Superpowers;
6. verify affected branch and E2E;
7. repeatability regression;
8. schedule proof if requested;
9. capacity/volume testing only if budget remains.

If a B/C/D blocker appears, stop burning engineering quota on that blocked node. Preserve already-PASS branches and surface the exact external/human action.

If the work window is being consumed without reaching the minimum real E2E, stop broad research and focus only on the single evidenced blocker. Do not add tools, redesign architecture, upgrade unrelated dependencies, or polish logs to use remaining time.

Quota exhaustion never changes the user’s definition of DONE. If all requested branches did not pass, report `FULL DONE = NO` and the exact remaining boundary.

## Failed-fix guard

Unexpected technical behavior belongs to Superpowers systematic debugging.

After three failed minimal fixes to the same defect, stop guessing. Re-open root-cause analysis and question the architecture only if the evidence supports that conclusion.
