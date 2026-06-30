# Agent guide — Almanac org profile

Instructions for AI agents editing the **GitHub organization profile** for
[almanac-data](https://github.com/almanac-data) (this repo publishes to
`almanac-data/.github`).

## What this repo is

| Piece | Repo | Scope |
|-------|------|--------|
| **Org landing** | This repo (`profile/README.md`) | Public face of The Almanac |
| **Org workspace** | `~/github/almanac-data` | Engine caretaker jump-in (symlinks to verticals) |
| **Verticals** | `climate-almanac`, `health-almanac`, … | Catalog contents only |
| **Engine** | `almanac-template` | Schema, scripts, CI |

**Catalog, don't host.** This repo has no `catalog/` — only org-level markdown.

## Where to work

| Task | Repo |
|------|------|
| Org README, catalog table, onboarding copy | **This repo** → PR here |
| Engine, propagation, cross-vertical scripts | `almanac-data` or `almanac-template` |
| Add/fix a dataset | One vertical's `catalog/*.yaml` |

Default org session root: **`~/github/almanac-data`**. Opening this repo directly is fine for
profile-only edits; cross-cutting work should use the meta workspace.

## Fleet / Willow rules

When `.mcp.json` is present (gitignored, materialized by project sync):

- **Worktree + PR** for every change; no direct commits to `main`.
- Shell via Kart (`willow_run` / `agent_task_submit`), not raw agent Bash.
- Handoffs use `project: almanac-data` (shared with the org workspace).
- Re-sync fleet wiring after registry changes:

```bash
cd ~/github/willow-2.0
./willow.sh project sync almanac-data-dotgithub
```

See [`../almanac-data/docs/DEVELOPMENT.md`](../almanac-data/docs/DEVELOPMENT.md) for the full
almanac fleet overlay.

## Invariants

1. Keep the catalog table accurate — dataset counts must match each vertical's `catalog.json`.
2. Link to vertical repos on GitHub (`almanac-data/<name>`), not local paths.
3. Do not duplicate vertical `AGENTS.md` engine rules here; link to `almanac-template` instead.

## Tone

Public-interest infrastructure. The org page orients contributors; vertical stewards own contents.
