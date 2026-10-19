# New Game (from gabebartolo-spec/game-template)

A Godot 4.7.2 game starter with every project rule already in place: `CLAUDE.md`, CI (sharded
Godot tests that count every test function, lint, secret scan, doc caps, Windows build), PR
template, status board, decision log, handoffs and the project skills under `.claude/skills/`.

## Kickoff checklist (the first session does this, then deletes this section)

GitHub does not fill in names, so a new repo made with **Use this template** starts generic:

1. Rename: `New Game` in `CLAUDE.md`, `project.godot`, `README.md`; the `game-` skill prefix in
   `.claude/skills/` if you want a project slug (e.g. `orcs-pr`).
2. Write the pillar sentence in `CLAUDE.md` (the line starting `PILLAR:`), with the director.
3. Load the `project-kickoff` skill and do its section 3 ("After the scaffold"): branch
   protection, the deliberately broken gate PRs, the document pack, role briefs.
4. The first item in `docs/STATUS.md` is assigned by the director.

## Rules

- Project rules: `CLAUDE.md` and `.claude/skills/game-*`.
- Rules for every project: `~/.claude/CLAUDE.md` and the skills it names (live source; backed up
  to the private `gabebartolo-spec/claude-kit`). `docs/RULES_GLOBAL.md` is a snapshot of it from
  when this template was last updated; if they differ, `~/.claude` wins.

## Tests

`GODOT=<godot console exe> tools/run_tests.sh` runs what CI runs.
