---
name: guazi-design-style-guide
description: Use when implementing UI that should match the `Guazi Design` Figma library, when the user shares the file key `IlDoKwM2KnSOdvFyFskkP6`, asks for Guazi-style pages/components, or wants a Figma-to-code workflow constrained by Guazi tokens, radii, typography, shadows, and published component names.
---

# Guazi Design Style Guide

## Overview

Use this skill when the target visual language is the `Guazi Design` Figma library. It helps Codex reuse the library's published components first, then fall back to token-aligned manual composition only when an exact component does not exist.

Load `references/guazi-design-reference.md` when you need the actual token values, component names, or composition rules.

## Workflow

1. Confirm the work should match the Figma library `Guazi Design` (`IlDoKwM2KnSOdvFyFskkP6`).
2. Search the design system with exact bilingual component names first, for example `Button 按钮`, `NavBar 导航栏 - H5`, `NavBar 导航栏 - mini program小程序`, `Tabs 选项卡`, `Input 输入框`, `Switch 开关`, `Avatar 头像`.
3. Reuse published components before drawing primitives or inventing local variants.
4. Apply the token rules from `references/guazi-design-reference.md` for color, radius, typography, and shadow.
5. If no exact compound component exists, compose from the nearest published primitives while keeping the same Guazi tokens and spacing rhythm.

## Rules

- Prefer Guazi-published components over custom wrappers, even when the component names are mixed Chinese/English.
- Treat the library as a Guazi-branded system built on TDesign-style token taxonomy. This is an inference from the library's documentation pages and token names; preserve the Guazi brand values, not raw Tencent blue defaults.
- Prefer `NavBar 导航栏 - H5` for web pages and responsive H5 screens. Use `NavBar 导航栏 - mini program小程序` only when the user explicitly asks for mini-program behavior.
- Keep rounded corners restrained to the documented scale: `2 / 4 / 8 / 12 / 999 / 50%`.
- Keep typography simple: regular and semibold are the dominant weights; use the documented line-height rule instead of ad hoc values.
- Prefer token-consistent grayscale text (`Font Gy1` to `Font Gy4`) over arbitrary slate/gray substitutions.
- Do not introduce a new accent color when the Guazi green ramp already covers the need.
- When coding from Figma, preserve the library's component hierarchy and state names where possible so the code can map back to the library cleanly.
- Page title bars should be fixed to the top of the viewport when the screen is a detail page or transactional H5 page.
- The title bar width should match the page content width; do not make it visually narrower than the main page shell.
- Title bars and content cards should default to border-separated surfaces without visible elevation. Only use shadows when the interaction semantics clearly require floating layers.
- Page layouts should adapt to the available viewport width instead of hard-coding a 375px page shell.
- Default H5 card spacing should use `10px` page outer padding, `10px` vertical gap between cards, and `14px` card inner padding unless a design explicitly overrides it.
- Cards should not use gray borders by default. Separate cards through spacing and white surfaces first, not outlines.

## Fallback Composition

When the library lacks a compound component:

- Build cards from Guazi token rules plus the closest published primitive components.
- Example: if there is no `AvatarCard`, compose it from `Avatar 头像` and a white card container using Guazi radius, text colors, and shadow tokens.
- Do not invent decorative effects, large glassmorphism surfaces, or oversized radii unless the source design explicitly shows them.
- For H5 detail pages, prefer a full-width fixed header plus a responsive content container instead of a floating mobile card stack.

## Resources

- `references/guazi-design-reference.md`: token values, component map, and implementation guidance extracted from the Guazi library.
