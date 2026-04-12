---
name: guazi-design-style-guide
description: Use when the target UI should follow the Guazi Design Figma library and the output must stay aligned with Guazi color, typography, radius, spacing, navbar, card, tag, form, and page-shell rules. Trigger on requests like "按瓜子规范实现", "按瓜子组件库出页面", "给我这个页面的设计规范", or when another skill needs Guazi rules as its visual authority.
---

# Guazi Design Style Guide

Use this skill as the visual authority for Guazi-style work inside WorkBuddy.

Read `references/guazi-design-reference.md` when you need the actual design rules, token values, component names, or page-shell constraints.

## When to use

- The user wants a page or component to match the Guazi design system
- The user provides the Guazi Figma library or a page that should visually align to it
- Another skill needs a stable source for spacing, header, card, and component usage decisions

## Workflow

1. Confirm the target visual language is Guazi
2. Load `references/guazi-design-reference.md`
3. Reuse published Guazi components first when the current workspace supports design-system reuse
4. Fall back to token-aligned manual composition only when an equivalent component is missing
5. Keep page shells, cards, title bars, and spacing consistent with the Guazi rules

## Rules

- Treat this skill as the base visual layer
- Prefer Guazi-published components over custom invention
- Prefer H5 title bars for web and responsive H5 pages
- Keep page title bars fixed for detail and transactional pages unless the requirement clearly says otherwise
- Default to restrained radius, no unnecessary shadows, and white-card separation through spacing
- Default H5 card spacing should use `10px` outer padding, `10px` vertical card gap, and `14px` card padding unless the source design overrides it
- Cards should not use gray borders by default
- If the current WorkBuddy environment does not support direct Figma or design-system tooling, still use these rules as the visual source of truth for code and layout decisions

## Resources

- `references/guazi-design-reference.md`
