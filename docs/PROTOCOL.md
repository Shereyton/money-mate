**Development Protocol**

- **Work Branch**: Do all changes in `MoneyPlayground`. Keep `main` untouched as a safety valve.
- **Safety Snapshot**: Before big changes, tag the current `origin/main` for rollback:
  - `git fetch origin`
  - `git tag -a "safety/main-baseline-$(date +%Y%m%d-%H%M%S)" $(git rev-parse origin/main) -m "Safety tag: snapshot of origin/main"`
  - `git push origin --tags`
- **PR Flow**: Open PRs from `MoneyPlayground` → `main` after testing. Merge only after review/approval.
- **Local Guardrail**: Enable the repo’s pre-push hook to block accidental pushes to `main`:
  - `git config core.hooksPath .githooks`
  - Attempting to push to `main` will be blocked locally with guidance.
- **Change Scope**: Keep changes focused; don’t modify unrelated code.
- **Docs**: Update `README.md` when behavior changes (e.g., income/check logic) to match the app.

This protocol ensures we can always revert back to a known-good `main` while iterating on `MoneyPlayground` safely.

