# Agent Job Board

**Your AI agents work for you. Manage them like it.**

Most people prompt their agents and hope. This is the system for running them like a company instead: every job posted like a real posting, every role mirrored on the highest-paid jobs on Earth, every project gated like a NASA readiness review, every hire graded — and every failure kept on the record, permanently.

It was designed agent-first: the source of truth is an append-only JSONL ledger that agents read and write directly. The human reads the board. The agents read the ledger.

---

## What's inside

**The roster** — [14 canonical roles](docs/talent-roster.md), each mirrored on a real top-of-market job (a Meta E8 Distinguished Engineer at ~$3.0M total comp for the Orchestrator, an OpenAI Research Scientist for the Evaluator, a Jane Street reviewer for the Auditor), with the role's actual skills and work pattern written into every brief. Default team: Orchestrator + Evaluator + Adversary. Specialists layer in.

**The tracker standard** — [11 practices](docs/tracker-pm-standard.md) borrowed from how elite programs actually run: the Heilmeier catechism as a genesis gate (no project exists until it answers all 8 questions), metrics declared before work starts, hill positions instead of percent-complete theater, appetite and circuit breakers from Shape Up, one owner and one forecast per project, author-closed problem records, delete-before-optimize.

**The blindspot protocol** — [24 named failure modes](docs/blindspot-protocol.md) (14 judgment traps like planning fallacy, sunk cost and HIPPO anchoring; 10 data traps like survivorship, Goodhart and silent missingness), each with a checkable rule. Decisions are scored with a formula, not a vibe:

```
AdjustedP  = BaseRate + EvidenceWeight × (CaseEstimate − BaseRate)
FinalScore = AdjustedP × DataQuality        DataQuality = geometric mean of
             (provenance, freshness, accuracy, coverage, uniqueness)
```

Weak data mechanically cannot outrank strong data. The supreme rule, in full: *let history and data and math do the work.*

**The judgment firewall** — [decision rights in 4 tiers](docs/judgment-firewall.md). Some decisions a mechanism makes. Some an agent makes, logged and scored. Some need to survive an adversary first. Some belong to the human alone. Per-category error budgets burn down and automatically escalate a decision's tier when a category keeps being wrong.

**The recursion stack** — [how the system improves itself](docs/recursion-stack.md) without rewriting its own constitution: outputs become data, outcomes become rules, the scorers get scored (a decision-regret ledger compares resolved decisions against the runner-up that wasn't taken), and the self-model is computed from records, never asserted.

## The ledger

Everything is one append-only file: `ledger.jsonl`. Roles, assignments, reviews, projects, milestones — one JSON object per line, history never rewritten, corrections appended. The format is documented in [docs/ledger-format.md](docs/ledger-format.md), with a runnable sample in [examples/](examples/sample-ledger.jsonl).

Why a ledger and not a database? Because the point is the record. A board that only shows wins is marketing. This one keeps the misses, the counter-evidence, and the grades — which is what makes the wins believable.

## Principles

1. **Proof over demos.** A claim ships with its receipt or it doesn't ship.
2. **Genesis before work.** Every project states where it came from and what done means, before the first task.
3. **Grade every hire.** Every agent assignment ends in a verdict: rehire, or retire the pattern.
4. **Failures stay.** Deleting a failure from the record is the one unforgivable edit.
5. **The human decides what only humans decide.** Everything else is a mechanism, a log entry, or an adversary's problem.

## Origin

Built in one night (October 2026) by a solo operator in Calgary running an AI agent fleet — four months into building with AI, no CS degree — to manage the fleet building a payment-authority product for a hackathon, a job search, and a small open-source portfolio. The first project the board ever tracked end-to-end shipped the same night: a local receipt sorter (on-device model, client data never leaves the laptop) whose demo was graded 15/15 against ground truth before it was accepted.

The board is now the operating system. This repo is its public spec.

## Roadmap

- Reference viewer: render any `ledger.jsonl` as the board (roles, verdict queue, project gates, integrity panel)
- Verdict Queue export: everything awaiting a human decision, sorted by cost of delay
- Ops Ledger: WIP caps, collision radar for deadline pile-ups, blocker recurrence tracking
- Templates: genesis records, review rubrics, decision packets

Built by Marcus Richards, directing AI coding agents.

## License

MIT. Copyright (c) 2026 Marcus Richards. See [LICENSE](LICENSE). Take it, fork it, run your fleet better than we run ours. Then tell us how.
