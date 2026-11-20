# Portable agent kit

Copy the **contents** of this folder into each repository root, preserving hidden `.agent/` directory. Keep `AGENTS.md` in the **repository root** so common coding agents can discover it.

## Install (without overwriting existing files)

From the new repository root, copy `AGENTS.md` and `.agent/` from this kit. Review conflicts if the target already has its own `AGENTS.md`.

## First-run process

1. Fill business/product fields in `.agent/project/PROJECT.md`.
2. Set `Active profile: react-vite-landing` for compatible Vite/React landing projects, or `none` for other stacks (and create a new profile only when useful).
3. Ask an agent to inspect the repository and fill verified technical facts plus `.agent/project/CONTEXT.md`.
4. Commit the kit, project intake and context with the repository. Do not store credentials.

## Reusing via GitHub

Maintain the generic kit in a GitHub **template repository**. To begin a project, either copy its contents or create a repository from the template and add application code. A normal `git clone` alone preserves the kit as a separate folder unless you copy its contents into the application root.

## Updating your master kit

Keep reusable defaults under `.agent/rules/` and `.agent/profiles/`. Keep project-specific facts under `.agent/project/`. When syncing kit updates into existing repos, preserve their project-specific `PROJECT.md`, `CONTEXT.md` and `DECISIONS.md`; never replace them with the blank master templates.

## Why root AGENTS.md remains small

Agents commonly auto-discover `AGENTS.md` but not arbitrary linked files. The root document explicitly instructs them to read the rest. This is a behavioral instruction, not a technical guarantee for every agent/tool. Codex also supports directory-scoped `AGENTS.md`; these are optional for special subtrees but are not necessary for this starter kit.

## Notes

- The React profile is a reusable default, not a claim that a new repository contains the listed dependencies.
- Example trees are illustrative and do not require empty folders.
- A user message or platform instruction can supersede repository rules.
