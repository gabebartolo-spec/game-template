# Status board

Cap: 150 lines. Edited only by the merge role, in a board PR after each merge, from the merged
PR's "Board and log" section. History rolls to `docs/archive/status_<month>.md`.

## Phase
Current phase: **0 — Foundations** (gate: CI proves it rejects a test function never called, a
test that makes no check, an untyped declaration and a planted secret). Gate signer: the lead.

## Agents

| Agent | State | Item | Branch / PR | Since |
|-------|-------|------|-------------|-------|
| Lead | working | kickoff | — | 2026-10-20 |

States: working · running a check · awaiting director · blocked · available.

## Assigned items (in order; an item starts only when it is listed here)

### Phase 0
1. Lead: push the scaffold, make the repo private or public per the director, protect `main`
   (`test`, `doc-caps`, `gitleaks` required; squash only; delete branch on merge).
2. Lead: `project.godot` with the autoload list and typing warnings as errors; the smoke suite
   green; the harness self-test green.
3. Lead: the deliberately broken PRs (an uncalled `_test_`, a test with no check, untyped script, planted
   `GAME_TEST_SECRET_` key); each must go red. Record the result in `docs/audits/`.
4. Lead: the document pack from the playbook kickoff checklist (vision, engine, machine, team,
   guardrails, style bibles, pipeline, roadmap, repo, licence register, open questions).
