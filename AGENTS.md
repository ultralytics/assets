# AGENTS.md

This file provides guidance to AI coding agents (Claude Code, etc.) when working with code in this repository. CLAUDE.md is a symlink to this file.

## Core Principles (CRITICAL)

Respecting these principles is critical for every PR.

**Less is more. The simplest solution is the best solution.**

The action hierarchy for every change: **Delete > Replace > Add**. The best code change is a deletion. The second best is modifying what exists. Adding new code is the last resort.

1. **Minimal**: The simplest solution that works. Do not over-engineer, over-abstract, or add code just in case. Three similar lines beat a premature abstraction. Avoid error handling for impossible states, feature flags, compatibility shims, or policy scaffolding unless they are truly required.
2. **Solve at the source**: Do not hack fixes. Solve problems at their root. If something is broken, fix or remove the broken thing. Never patch over a broken abstraction, add workarounds, or add synchronization code for state that should not be duplicated.
3. **Delete ruthlessly**: When replacing code, delete what it replaced. Remove unused imports, functions, types, files, and commented-out code. Git preserves history. Run the repo's relevant dead-code or cleanup check when available.
4. **Replace > Add**: Modify existing code over adding new code. Edit existing files, extend existing components or functions with minimal parameters, and reuse existing utilities. If creating a new file, first prove it cannot fit cleanly in an existing file.
5. **Check existing**: Search the entire repo before creating anything new. If a feature, component, helper, responder, workflow, or utility already solves a similar problem, reuse or adapt it and delete the duplicate path.
6. **Deduplicate**: Do not duplicate existing code when updating the repo. Consolidate or refactor duplicates you find when it is in scope and low risk.
7. **Zero Regression**: Do not break existing features or workflows unless the PR intentionally removes them with evidence.
8. **Production ready**: All changes must be thoroughly debugged, validated, and production ready.

**When fixing bugs, ask: "What can I delete?" before "What can I replace?" before "What should I add?"**

## PR Workflow

After opening a PR:

1. Wait for the automated PR review and auto-format commit from Ultralytics Actions (`format.yml`), then pull and address every finding.
2. Launch an independent adversarial review agent with cold context (just the PR diff and this file) to hunt for bugs, regressions, and Core Principles violations — use the Codex CLI, one fresh `codex exec` run per round. Fix, push, and repeat until a fresh run reports LGTM.
3. Never fight other commits: Ultralytics Actions pushes auto-format and header commits, and multiple users may work on the same PR. `git pull --rebase` before pushing; never force-push, reset, or revert commits you did not author.
4. After the PR merges, clean up: remove local worktrees and branches for it, then `git checkout main && git pull`.

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
