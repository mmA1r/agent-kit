# Documentation and Context Maintenance

## Document roles

- `PROJECT.md`: user-owned intent and constraints, plus repository-verifiable facts. Not a changelog.
- `CONTEXT.md`: agent-maintained current architecture, confirmed patterns, significant decisions and outstanding risks. Not a task transcript.
- `DECISIONS.md`: concise durable architectural decision records when tradeoffs are substantial.
- `AGENTS.md` and `rules/`: reusable instructions, not evolving project facts.

## Update triggers

Update `CONTEXT.md` in the same task when you:
- change routing, state ownership, component/module boundaries, data flow, build/deploy conventions, or design tokens;
- add/remove a dependency or major asset pipeline;
- discover an important documented assumption is false;
- establish a durable convention that future agents will need.

For significant tradeoffs, append a dated decision entry to `DECISIONS.md` with context, decision, consequences and alternatives. Avoid logging trivial edits.

## Accuracy requirements

- Inspect code/config before asserting project facts. Mark unverified details `UNVERIFIED` and don't present them as settled.
- When documentation conflicts with code, report the conflict, update the stale documentation if evidence is clear, and avoid silently changing user-owned product intent.
- Preserve developer-written context and decisions; refine rather than overwrite.
- Never write passwords, API tokens, private customer data or personal secrets.
- Keep documents compact, with meaningful links to actual files and no giant copied code excerpts.
- At task completion, mention documentation updates when they materially affect future work.
