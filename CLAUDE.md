# CLAUDE.md

Daily job that counts active matches in the partitelle-bot database and appends a row to Google Sheets.

## Read first
- [README.md](README.md) for environment variables and the GitHub Actions setup.

## Rules
- Small, focused PRs. There is no test suite or linter in this repo yet: run `python main.py` against a non-prod schema (`PB_DB_SCHEMA`) when changing behavior, and say in the PR how you checked it.
- Branches are `feat/...` style and commits use Conventional Commits, as in the history.
- Never commit credentials; they live in GitHub Actions secrets.
- The schema it reads (`active_match` view) belongs to partitelle-bot: coordinate changes there.

## Gates
- Never push to `main`; open a PR.
- The workflow runs on a daily schedule against the real database. Merging and changing secrets or the schedule need a maintainer's explicit OK.

Company context: if you have access to the private repo `partitelle/hq` (usually cloned at `../partitelle-hq`), read its CLAUDE.md for decisions, priorities and approval rules. This repo must stay self-contained without it.
