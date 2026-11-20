# Quality, Accessibility and Performance

## Quality

- Keep public APIs explicit; handle empty/error/loading cases when the feature needs them.
- Use the existing testing stack. Do not add testing tools without a request.
- Make testable logic pure where practical, and avoid hidden side effects.
- Respect existing browser support and bundler constraints specified in `PROJECT.md`.

## Accessible UI (when applicable)

- Use semantic HTML, native buttons for actions, anchors for external navigation, and the framework router's links for internal navigation.
- Every meaningful image needs useful alt text; decorative images use `alt=""`.
- Inputs have programmatic labels. Interactive elements have visible focus indicators and keyboard support.
- Expandable controls expose `aria-expanded`; use `aria-controls` when they control a region.
- Handle Escape and focus management for dialogs/menus; use appropriate dialog semantics and focus trapping for modal dialogs.
- Honor `prefers-reduced-motion` for nonessential motion.

## Performance

- Measure before adding complex optimizations; prevent clearly unnecessary re-renders or large shared state.
- Load noncritical images lazily and give images stable dimensions where possible.
- Lazy-load sufficiently heavy routes and media when doing so improves the experience without delaying critical content.
- Avoid pulling heavy 3D/media modules into shared entry points where they are not needed.
- Prefer CSS for simple visual transitions; constrain imperative animation to its own lifecycle and scope.
