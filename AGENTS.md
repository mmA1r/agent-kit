# Repository Agent Instructions

This file is the entry point for coding agents. Read the referenced documents; files under `.agent/` are **not** assumed to be automatically discovered.

## Required reading order

At the start of each task, read:
1. `.agent/rules/01-workflow.md`
2. `.agent/project/PROJECT.md`
3. `.agent/project/CONTEXT.md`
4. `.agent/rules/02-architecture.md`
5. `.agent/rules/03-code-style.md`
6. `.agent/rules/04-quality.md`
7. `.agent/rules/05-documentation.md`

Then read the profile specified by `Active profile` in `PROJECT.md` (if present). Read only task-relevant additional documentation.

## Project intake gate

`PROJECT.md` contains required fields marked `[REQUIRED]`. Treat empty values or `UNSET` as missing.

- On **every new task**, inspect the required fields and report missing ones briefly **before making code changes**: `Project setup incomplete: <field names>.` This is a mandatory reminder, not a one-time suggestion.
- Infer missing values only from verifiable repository evidence (package manifests, source code, configuration, README). If confident, write the verified value to `PROJECT.md` and record the evidence in `CONTEXT.md`. Never invent product goals, audience, deadlines, or deployment requirements.
- If missing information is not essential to the requested task, proceed with conservative, reversible assumptions after the reminder. If essential, ask one focused question and avoid speculative implementation.
- Do not repeatedly remind about intentional empty optional fields.

## Source of truth and priority

Follow system/developer/user instructions first. Within repository documents, explicit task instructions and verified code/config take precedence over stale descriptions. `PROJECT.md` decides which optional profile applies. Shared rules establish defaults; profile rules refine them for their stack. Report incompatible requirements instead of silently picking one.

## Change contract

Before editing: inspect relevant code and follow its existing patterns unless they violate an explicit rule. Scope changes to the task; avoid speculative abstractions and new dependencies.

After editing: run applicable checks available in the repository, inspect changed imports/paths, and summarize changes, checks and any unresolved issues. Update `.agent/project/CONTEXT.md` when a durable architectural decision or non-obvious constraint changes. Never record secrets in these files.
