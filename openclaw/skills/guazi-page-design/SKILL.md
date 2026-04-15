---
name: guazi-page-design
description: "Use when the user wants a reusable Guazi page-generation workflow in OpenClaw: accept a requirement document, prototype image or Figma reference, or prototype HTML; identify the dominant page type automatically; apply Guazi global rules, component rules, and page-pattern rules; then generate a frontend page or structured page plan. Trigger on requests like '根据需求生成页面', '根据原型图生成页面', '根据 HTML 原型生成页面', '自动识别页面类型', '按规范生成列表页/详情页/表单页', or '按瓜子规范出页面'."
metadata:
  openclaw:
    user-invocable: true
    slash-command: guazi-page-design
    emoji: "🧩"
    homepage: "https://github.com/Doris-ys/Guazi-PageDesign"
---

# Guazi Page Design

Use this skill for Guazi-style page delivery inside OpenClaw.

Pair it with the sibling skill:

- `$guazi-design-style-guide`

Use the routing references below to determine input source, page type, component selection, and page scaffold:

- `references/guazi-input-source-routing.md`
- `references/guazi-page-type-routing.md`
- `references/guazi-component-usage.md`
- `references/guazi-navbar-component.md`
- `references/guazi-input-component.md`
- `references/guazi-upload-component.md`
- `references/guazi-tabs-component.md`
- `references/guazi-search-component.md`
- `references/guazi-button-component.md`
- `references/guazi-tag-component.md`
- `references/guazi-dialog-component.md`
- `references/guazi-toast-component.md`
- `references/guazi-list-page-layout.md`
- `references/guazi-standard-list-examples.md`
- `references/guazi-detail-page-layout.md`
- `references/guazi-standard-detail-examples.md`
- `references/guazi-form-page-layout.md`

## Required outcome

Every run should try to produce one of these outcomes, depending on the tools available in the current OpenClaw environment:

1. A ready-to-implement frontend page
2. A componentized page specification
3. A page delivery plan with clear sections, states, and component mapping

If the environment also supports Figma or design-system write-back, include that as an optional final step. If not, do not block on it.

## Workflow

### 1. Identify the input source

- Use `references/guazi-input-source-routing.md`
- Classify the source as requirement document, prototype image/Figma, prototype HTML, or mixed input
- If the input is a prototype image or screenshot, first analyze its structure (page shell, section order, card hierarchy, action hierarchy), then generate with Guazi rules instead of copying raw visual styles
- Resolve conflicts in this order:
  - business rules -> requirement document
  - layout structure -> prototype image or prototype HTML
  - final visual language -> Guazi rules

### 2. Identify the page type

- Use `references/guazi-page-type-routing.md`
- Route the page into one dominant pattern:
  - list page
  - detail page
  - form page
  - hybrid page

### 3. Load the rule stack

- Always apply `$guazi-design-style-guide`
- Always apply `references/guazi-component-usage.md`
- Add component-specific references only when the page actually uses them
- Add `references/guazi-button-component.md` when the page has explicit CTA rows or list-card actions
- Add exactly one dominant page-pattern reference:
  - list -> `references/guazi-list-page-layout.md`
  - detail -> `references/guazi-detail-page-layout.md`
  - form -> `references/guazi-form-page-layout.md`
- For list and detail pages, also load the nearest standard example reference

### 4. Generate the page solution

- Translate the requirement into explicit sections
- Map each section to the correct Guazi component or layout primitive
- Keep the output aligned to Guazi spacing, title-bar, card, and CTA rules
- Include loading, empty, error, and critical business states whenever relevant

### 5. Deliver according to environment capability

- If OpenClaw can edit code in the current workspace, generate or update the page code
- If OpenClaw is being used for planning only, output a structured implementation plan
- If OpenClaw has design integration available, optionally produce a Figma sync or handoff step
- If direct Figma sync is unavailable, output a Figma-ready handoff checklist instead of blocking

## Practical rules

- Do not invent the page scaffold before choosing the page type
- Do not let prototype styling override Guazi visual rules
- For prototype-image inputs, use the prototype as structure source only; enforce Guazi design rules for style and component choice
- Treat prototype HTML as structural input, not the final style source of truth
- Prefer H5 navbar patterns for responsive web pages
- Use component rules before inventing custom widgets
- For hybrid pages, use the dominant pattern for the shell and the secondary pattern only inside the relevant section

## Deliverables checklist

Before finishing, confirm:

- input source was identified
- page type was identified
- Guazi visual rules were applied
- component rules were applied
- page sections and states are explicit
- the output format matches the current OpenClaw environment

## Resources

- `references/guazi-page-design-reference.md`
- `references/guazi-input-source-routing.md`
- `references/guazi-page-type-routing.md`
- `references/guazi-component-usage.md`
- `references/guazi-navbar-component.md`
- `references/guazi-input-component.md`
- `references/guazi-upload-component.md`
- `references/guazi-tabs-component.md`
- `references/guazi-search-component.md`
- `references/guazi-button-component.md`
- `references/guazi-tag-component.md`
- `references/guazi-dialog-component.md`
- `references/guazi-toast-component.md`
- `references/guazi-list-page-layout.md`
- `references/guazi-standard-list-examples.md`
- `references/guazi-detail-page-layout.md`
- `references/guazi-standard-detail-examples.md`
- `references/guazi-form-page-layout.md`
