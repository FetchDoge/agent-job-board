# Tracker PM Standard v1 — how projects on the Agent Job Board are run

Fused 2026-10-13 from two research lanes on the world's best project/program management (Meta/Google staff PM practice, Amazon Working Backwards + WBR, Cagan's product operating model, Shape Up, DARPA/Heilmeier, NASA lifecycle gates + SRB, Skunk Works, Toyota A3 + chief engineer, SpaceX's algorithm, Anthropic/Meta TPM practice). Adopted on the operator' instruction to apply the research to real scenarios and make it recursive where it benefits most.

## The standard

1. **Heilmeier genesis gate (DARPA).** No project earns a progress bar until its genesis record answers the eight questions in plain language: what it does, how it's done today and its limits, what's new and why it will succeed, who cares, risks, cost, duration, and the pre-registered midterm and final exams. A project that can't answer doesn't start.
2. **Declared metrics before work (Meta/Google PM + Amazon).** Each project declares 1–3 success metrics and 2–3 controllable input metrics, each with a named owner, before work starts. A project without metrics reports activity, never progress.
3. **Outcome over output (Cagan).** The progress bar moves only when the declared outcome metric moves. Tasks and features completed are logged as activity. If the outcome hasn't moved after a work cycle, the current approach is retired — not the objective — and a new approach is registered before more work is logged.
4. **Hill positions per scope (Shape Up).** Each project decomposes into scopes. Each scope is uphill (unknowns remain; the unknown is named) or downhill (execution only). Positions are snapshotted at each review; a scope frozen across two consecutive reviews auto-escalates: help, split, or kill.
5. **Appetite + circuit breaker (Shape Up).** Each project carries a fixed effort budget set before work starts. Scope flexes to fit the appetite. Anything unfinished when the budget ends must be re-pitched to continue — no automatic rollover.
6. **Gates, not drift (NASA + DARPA).** Progress is granted at readiness gates with pre-published entrance/success criteria and required artifacts, assessed by a reviewer who does not own the work. Milestone effort unlocks in tranches; a missed exam defaults to rescope-or-kill, never silent extension.
7. **One owner, one forecast (Skunk Works).** Every project has a single named owner with real authority. The standing health metric is projected effort-to-completion, refreshed on a fixed cadence — a forecast, not rear-view spend. A review that surfaces zero problems is treated as a failed review and dug into.
8. **Problem records, not status colors (Toyota A3).** Any blocked or slipping item carries a one-screen record: gap vs. target, observed evidence, root-cause hypothesis, countermeasure with a named owner, and a dated check. No problem record, no "in progress."
9. **Author-closed actions + logged dissent (NASA SRB).** An issue closes only when whoever raised it accepts the resolution. Unresolved dissent is preserved on the record and escalated, never averaged away or silently dropped.
10. **Delete-before-optimize audits (SpaceX).** On a fixed cadence, every tracked item is re-justified from first principles: named owner, value-vs-floor ratio on the biggest items. Nothing gets accelerated or automated until it survives a deletion review. Bloat is a tracked metric.
11. **Scaffolding as data (Anthropic/Meta TPM).** Roadmaps, DRI assignments, dependency sequences, decision logs, and escalation paths live as structured tracker artifacts — the single source of truth. Every escalation arrives with evidence and a recommended course of action, or it doesn't escalate.

## The recursion (where the loop pays most)

- **Estimate calibration.** Actual durations and outcomes from the job board feed the next project's appetite and forecast. Shape Up budgets and Skunk Works forecasts are set from recorded reality, not optimism; forecast error is itself tracked per project.
- **Gate quality.** Quarterly, projects that passed the Heilmeier gate are compared against slippage and outcomes. Gate questions that failed to predict trouble are tightened; questions that never discriminate are cut.
- **Practice pruning (weekly review).** The Monday review scores this standard the way it scores claims: each practice is kept only if it changed an outcome in the period. Practices that produced only ceremony are pruned, per the the operating charter recursion rules.
- **Briefs carry the standard.** Coordinator and lane-lead subagent briefs include the applicable rules above, so the workforce runs under the standard and its output data flows back into the board — the loop that makes the next team better than the last.

## Live application (2026-10-13)

- **Receipt Sorter.** Appetite: half-day build. Pre-registered exam: the demo ledger scored field-by-field against fixture ground truth. Scopes: runtime (uphill — unknown: whether Gemma installs and serves on this VM), pipeline (downhill, built), demo (uphill until runtime lands), submission draft (downhill once the demo verifies).
- **Permit.** Midterm exam: M2, Fri Oct 16. Standing forecast and problem records apply to the open PRs (#26, #27) and the remaining compliance items; slippage is flagged the same day (Muse's assigned role).
- **Graph Hacks entry.** Genesis answered in the prep packet; final exam: submission Oct 18. Build scope starts uphill (FalkorDB integration unknowns) at the Oct 14 kickoff check.
- **Muse upgrade program.** Final exam: the first claims-ledger scoring, Mon Oct 19 weekly review — the proven self-rating gets set there.
