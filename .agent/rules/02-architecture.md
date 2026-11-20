# Architecture and Ownership

## General rules

- Structure code by feature/domain and responsibility, not by file type alone.
- Keep implementation close to its nearest real owner. Promote to shared scope only after there are genuinely independent consumers.
- Prefer explicit boundaries and straightforward data flow. Do not add a service, context, hook, adapter or configuration layer without a concrete reason.
- Split large files along meaningful responsibilities; do not fragment small cohesive components.
- Keep offline scripts separate from runtime services and UI components.
- Move files only when required by the task; update static imports, dynamic imports, aliases, tests, and asset paths after moves.

## Component ownership for component-based UI projects

- Every extracted component has its own PascalCase directory with matching PascalCase component filename.
- Its local stylesheet belongs inside the same directory; do not create empty stylesheets.
- Components owned by a single parent are nested below that parent, recursively.
- Shared components live at the nearest common owner; use global `components/ui` only for truly app-wide primitives.
- Small, cohesive JSX fragments may stay inline rather than being extracted unnecessarily.

Example:

```text
features/
  home/
    components/
      Hero/
        Hero.tsx
        hero.scss
        HeroMedia/
          HeroMedia.tsx
          heroMedia.scss
    hooks/
      useHeroVisibility.ts
    data/
      heroContent.ts
    pages/
      HomePage/
        HomePage.tsx
```

## Functional modules

- Place hooks, utilities, schemas/types, constants, services, shaders and scripts under the relevant feature/domain.
- Organize substantial service domains by responsibility (scene, materials, lighting, interaction, rendering, preparation), never by a single broad technology folder alone.
- Do not create empty folders or deep chains of single-file directories.
- Place app-wide providers, routing and shared styles in `app/`; truly reusable cross-feature code in `shared/`.

These are defaults for **new or extracted code**. Existing structure remains intact unless in-scope changes justify migration.
