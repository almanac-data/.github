# Contributing

These repos share one working method, whether the contributor is a
person or an agent.

## The method

- **One bite at a time.** A PR delivers one outcome. If two unrelated
  changes rode the branch, flag them so they can be reviewed or split.
- **Receipts, not claims.** The PR template asks for Evidence — check
  only what you actually ran, and state the result ("144 passed"), not
  the intention ("tests should pass").
- **Verify in a clean environment.** A shared venv can mask a missing
  dependency that a fresh CI runner will catch. If you touched
  dependencies, prove the suite in a clean venv before pushing.
- **Fail closed.** When a check can't prove something is safe, it
  blocks. Don't ship a gate that can be ignored.
- **Archive, don't delete.** Stale things get marked as archived with
  an honest description — history is a record, not a scratchpad.
- **One implementation, no drift.** If the same logic exists in two
  places, extract it; don't patch both.
- **Match the house style.** Read the surrounding code first. Linters
  are configured to accept deliberate styles — don't "fix" them.

## Practical bits

- PRs use the closeout template (Bite / What was done / Evidence /
  Out of scope / Next bite). It's inherited everywhere.
- CI must be green before merge. Lint gates are enforced where the
  tree is clean; keep it that way.
- Dependency changes: run `pip-audit` if you can; dependabot patrols
  weekly regardless.
- Security findings go through [SECURITY.md](SECURITY.md), not issues.
