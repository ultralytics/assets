# AGENTS.md

This file provides guidance to AI coding agents (Claude Code, etc.) when working with code in this repository. CLAUDE.md is a symlink to this file.

## Core Principles (CRITICAL)

**Less is more. The simplest solution is the best solution.** The action hierarchy for every change: **Delete > Replace > Add**.

1. **Solve at the owner**: Put behavior in the code path that owns or observes it. For fixes, never guard a symptom with a staleness check, initialization flag, skip-first-call branch, or `try/except` around broken logic; relocate the trigger and delete the wrong path. For features, extend the existing owner rather than creating a parallel abstraction.
2. **Search and reuse first**: Search the whole repository before creating a feature, component, helper, workflow, or utility. Reuse or adapt what exists, consolidate in-scope duplication in the shared owner, and delete duplicate paths. Three similar lines beat a helper nobody else calls.
3. **Delete and modify existing code before creating new code**: Bugfixes are net-negative by default unless deletion and relocation are demonstrably impossible. A new file must first prove it cannot fit cleanly in an existing owner.
4. **Keep scope minimal**: Implement only the simplest complete solution. Avoid impossible-state handling, speculative flags, compatibility shims, policy scaffolding, and unrelated cleanup. Tests are out of scope by default — rely on existing coverage and focused validation; only an uncovered, high-risk regression path justifies minimal new test code.
5. **Ship zero-regression, production-ready changes**: Understand what you remove instead of retaining broken code as insurance. Remove unused imports, functions, types, files, and comments; run relevant cleanup checks; and thoroughly debug and validate the changed owner. Do not break existing features or workflows unless the PR intentionally removes them with evidence.

**Review gate:** for every addition, the reviewer decides whether deleting or changing existing code would have fixed the problem instead — if it would, that is a blocking finding. A missing or thin PR description is never itself a finding.

NEVER push to `main`. NEVER force push. Always start work in a new git worktree (`git worktree add`) on a feature branch and open a PR — never edit the primary checkout directly, it may hold in-flight work.

## PR Workflow

After opening a PR:

1. Wait for the automated PR review and auto-format commit from Ultralytics Actions (`format.yml`), then pull and address every finding.
2. Review the full diff in-session against the Core Principles, performance, and the review gate above, then batch the fixes into one commit and push. After each round of bot or human commits, pull and resume the same reviewer on `<last-reviewed-sha>..HEAD` plus anything that delta could have invalidated. Repeat until the local head matches the live head.
3. Hand off or merge only on a clean final pass: one cold full-diff review returning LGTM with no findings, on a head that is still live at merge time.
4. Never fight other commits: Ultralytics Actions pushes auto-format and header commits, and multiple users may work on the same PR. `git pull --rebase` before pushing; never reset or revert commits you did not author.
5. After the PR merges, clean up: remove local worktrees and branches for it, then `git checkout main && git pull`.

## Commands

```bash
# No build or test suite exists — this repository contains only static assets and Markdown
npx prettier --write --print-width 120 "**/*.md" "**/*.yml" # approximates the prettier step in format.yml
uvx codespell                                               # spell-check (format.yml, spelling: true)
```

`.github/workflows/format.yml` is the formatting source of truth: a single `ubuntu-latest` job (no matrix) running `ultralytics/actions@main` with `python: false` (no Python files) and `links: false`. PRs also get a GitHub default-setup CodeQL check (no workflow file in the repo).

## Architecture

This repository hosts the shared static assets for the Ultralytics ecosystem — there is no source code. It serves two roles:

- **Committed files on `main`** (logos, banners, docs images, social icons) are consumed by external sites and repos via `https://raw.githubusercontent.com/ultralytics/assets/main/...` URLs. Published paths are a stable public API: renaming, moving, or deleting a file breaks every external reference to it, so treat such changes as breaking.
- **GitHub Releases** host the pretrained model weights (`.pt`) and dataset archives that Ultralytics libraries auto-download when a requested file is not found locally (e.g. release `v8.4.0` for YOLO26). These binaries live in release assets, never in the repo tree.

Releases are cut manually via `.github/workflows/tag.yml` (`workflow_dispatch` only), hard-gated to `github.repository == 'ultralytics/assets' && github.actor == 'glenn-jocher'`; it pushes the tag and generates release notes with `ultralytics-actions-summarize-release`.

## Conventions

- Ultralytics Actions adds AGPL-3.0 license headers to workflow/YAML files automatically — don't add or revert them manually.
- Prettier (Markdown/YAML/JSON/CSS) and codespell run on every PR via `format.yml`; expect an auto-format commit pushed to your branch.
- `README.md` and `README.zh-CN.md` must stay in sync — apply any README change to both.
- Release tags (e.g. `v8.4.0`) track `ultralytics` package minor versions; there is no version file in this repo to bump.
- Binary assets are committed directly; prefer compressed formats already in use (`.avif` for docs images, `.svg` for logos).
