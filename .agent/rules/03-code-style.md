# Code Style

- Match the language, module system, formatter and lint configuration in the repository. Do not impose TypeScript on a JavaScript-only project or vice versa.
- Name files for their contents and responsibility: `ComponentName.tsx`, `componentName.scss`, `useSomething.ts`, `calculatePrice.ts`, `FEATURE_FLAG.ts` as applicable.
- Avoid generic catch-all files (`utils.ts`, `helpers.ts`) when the responsibility can be named accurately.
- Prefer explicit inputs/outputs, immutable updates and pure helpers for business logic.
- Never use TypeScript `any`; prefer accurate types or `unknown` with narrowing.
- Do not mutate React state, props, route definitions or imported constants.
- Avoid obvious comments and redundant explanations; document non-obvious tradeoffs and invariants.
- Name meaningful layout, animation and timing constants rather than scattering unexplained magic numbers.
- Avoid premature memoization, component extraction or abstractions.
- Follow local naming conventions where they are explicit; when they conflict with this guide, limit renaming to in-scope code and describe the deviation.
