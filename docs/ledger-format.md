# Ledger format

The board's source of truth is one append-only file: `ledger.jsonl`. One JSON object per line. History is never rewritten — a correction is a new line that references the line it corrects.

## Record types

### `role`
A canonical job on the board, mirrored on a real top-of-market role.

```json
{"type":"role","role_id":"orchestrator","title":"Orchestrator","mirror":"Distinguished Engineer (E8) — big-tech flagship AI org","comp_anchor":"~$3.0M total comp (levels.fyi, top of band)","owns":"Decomposition, staffing, integration, final call on reversible items","skills":["systems decomposition","evaluation design","evidence-led communication"],"status":"canonical"}
```

### `assignment`
One hire: a role, a task, a brief, a timebox. Ends in a `review`.

```json
{"type":"assignment","assignment_id":"a-001","role_id":"operator","task":"Stand up the local model runtime and verify it answers","brief":"End-to-end ownership; correctness is part of performance; report failures by mode, never as 'it didn't work'","timebox_min":90,"status":"in_flight","started":"2026-10-13T01:00:00-06:00"}
```

### `review`
The grade. Every field is mandatory — a review without counter-evidence is rejected by the integrity check.

```json
{"type":"review","assignment_id":"a-001","grade":"A-","verdict":"rehire","minutes":62,"deliverable_verified":true,"counter_evidence":["two failed download routes burned 25 minutes before the working one was found"],"notes":"Delivered the full chain and documented the substrate quirk for the next hire."}
```

### `project`
A tracked project. No project exists without a genesis and a target definition of done.

```json
{"type":"project","project_id":"receipt-sorter","name":"Receipt Sorter — local-first freelancer tool","kind":"tool","genesis":{"date":"2026-10-13","origin":"A contest listing plus a privacy gap: freelancers send receipts to cloud AIs because local tools are painful.","repo":"(local until published)"},"target_done":"Public repo + submission post live; demo scores full marks against ground truth","milestones":[{"name":"Pipeline proven on fixtures","done":true},{"name":"Repo published","done":false}],"status":"in progress"}
```

### `milestone`
A gate event on a project: claimed, then granted only on evidence.

```json
{"type":"milestone","project_id":"receipt-sorter","name":"Pipeline proven on fixtures","state":"granted","evidence":"demo scored 15/15 fields against ground truth","date":"2026-10-13"}
```

## Rules

1. **Append-only.** Never edit or delete a line. Supersede with a new line that names what it replaces.
2. **No names.** Personal and company names of private parties never appear in the ledger. Public roles and public companies (as mirrors) are fine.
3. **Progress is granted, not asserted.** A milestone flips only with an `evidence` field. A progress percentage is either labeled a stated figure or derived from granted milestones — never invented.
4. **Reviews require counter-evidence.** Every grade records what went wrong or what almost did. A spotless review is treated as a missing review.
5. **Burn is computed, not felt.** Time, cost and error budgets come from the records, never from narrative.
