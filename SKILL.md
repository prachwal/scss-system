---
name: scss-system
description: Use when designing or refactoring SCSS-based design systems with tokens, mixins, functions, color palettes, typography, spacing, responsiveness, and theming.
---

# SCSS System Skill

Use this skill when building a scalable SCSS architecture for components, pages, or a design system.

## Core approach

1. Start from tokens, not components.
2. Keep tokens semantic where possible: color, space, size, radius, shadow, z-index, motion.
3. Prefer mixins and functions for repeated patterns, not copy-pasted declarations.
4. Keep component styles small and composable.
5. Make responsive and themeable behavior a first-class requirement.

## Workflow

1. Identify the styling layer you need:
   - `tokens` for values
   - `mixins` for repeatable declarations and media queries
   - `functions` for computed values
   - `components` for reusable UI blocks
2. Define tokens first.
3. Add mixins only when the pattern repeats or requires conditional logic.
4. Use functions for calculations, scale transforms, and token lookups.
5. Keep component partials focused on a single responsibility.
6. Verify naming, spacing scale, contrast, and responsive behavior before expanding the system.

## Recommended structure

- `styles/tokens/`
- `styles/tools/` for mixins and functions
- `styles/base/` for resets and typography
- `styles/components/`
- `styles/utilities/`
- `styles/themes/`

## Rules of thumb

- Prefer `!default` for configurable tokens.
- Prefer semantic variables like `$color-surface` over raw hex in component files.
- Prefer one source of truth for spacing and type scale.
- Keep media queries centralized when possible.
- Use mixins for breakpoint wrappers, fluid type, truncation, visually hidden content, and theme variants.
- Avoid deeply nested selectors and selector chains that are hard to override.
- Keep specificity low and predictable.
- Validate color contrast in both light and dark themes.

## When to add a mixin

- You repeat the same declaration block in multiple files.
- A pattern needs parameters, such as size, color, or breakpoint.
- A utility-like pattern should stay consistent across components.

## When to add a function

- You need derived values from tokens.
- You are building a scale, clamp calculation, or spacing conversion.
- You need consistent unit math.

## Output expectations

When asked to produce SCSS for a system:
- define tokens first
- show the file structure if helpful
- keep examples practical and reusable
- explain how a component consumes tokens and mixins

## References

- [references/tokens.md](references/tokens.md): token layers, scales, and naming
- [references/mixins.md](references/mixins.md): mixin patterns and examples
- [references/components.md](references/components.md): component styling guidance
