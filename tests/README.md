# Tests

One command runs everything CI runs (import, every suite, the harness self-test):

```sh
GODOT=/path/to/godot_console tools/run_tests.sh            # everything
GODOT=/path/to/godot_console tools/run_tests.sh smoke      # some suites
QUICK=1 GODOT=/path/to/godot_console tools/run_tests.sh smoke   # local loop, no re-import
```

Every run gets its own user data (APPDATA and the XDG dirs point at a temp dir), so two
agents' runs never share saves, settings or caches. The rules are the `game-architecture`
skill §6 and the `game-godot-tests` skill: one runner per suite extending
`tests/lib/runner.gd`; each test is a `_test_*` method that `run_checks()` calls through
`await _t("_test_name")`, and the summary reads "K of M functions, N checks, F failures"
(`tests/functions_ran.gd`): a test never called, or one that made no check, fails by name.
A `SCRIPT ERROR` fails the suite; seeds pinned. Nothing is registered by hand: no floors,
suites found by filename, CI shards split from `tools/ci_timings.txt` by
`tools/plan_ci_shards.sh` (director 2026-10-19, github-hygiene §4). Add a row to the table.

## Suites

| Suite | Covers |
|---|---|
| `smoke` | typing warnings are errors; exactly the sanctioned autoloads; every script compiles; the main scene opens headless and stays up |

The harness self-test (`tools/test_run_tests.sh`) proves the runner fails a suite with a test
function nobody calls and one whose test made no check (fixtures in `tests/fixtures/`), and
that an untyped declaration does not compile.
