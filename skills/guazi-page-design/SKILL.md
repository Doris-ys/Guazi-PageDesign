---
name: guazi-page-design
description: "Use when the user wants a reusable end-to-end Guazi page-generation workflow: accept a requirement document, prototype image/Figma, or prototype HTML -> identify the page type automatically -> apply global design rules, component-usage rules, and page-pattern rules -> implement the frontend page -> send the page back to Figma. Trigger on requests like '根据需求生成页面', '根据原型图生成页面', '根据 HTML 原型生成页面', '自动识别页面类型', '按规范生成列表页/详情页/表单页', '把页面回传到 Figma', or when the page must be delivered both as code and as a 375px Figma screen using Guazi library components."
---

# Guazi Page Design

## Overview

Use this skill for the full delivery loop:

1. Read a page requirement
2. Identify the page type automatically
3. Apply the correct rule layers
4. Build the frontend page in code
5. Preview and verify the page
6. Send the page back to Figma
7. Build a componentized Figma version that reuses the Guazi design library

## Quick Route

Use this skill when the user provides any of these:

- requirement document
- prototype screenshot or Figma source
- prototype HTML
- mixed source set

Default execution order:

1. identify input source
2. identify page type
3. load the right rule stack
4. build code first
5. verify locally
6. sync to Figma
7. rebuild a `375px` componentized Figma frame with Guazi instances

## Reference Map

This skill assumes the target visual language is Guazi. Pair it with `$guazi-design-style-guide` for design decisions, and with the Figma skills for canvas work:

- `$guazi-design-style-guide`
- `$figma-generate-design`
- `$figma-use`

Use the following references as a routing tree.

### Core Routing

- `references/guazi-input-source-routing.md`: identify whether the input is a requirement document, prototype, prototype HTML, or a mixed source set
- `references/guazi-page-type-routing.md`: identify the dominant page type from the requirement
- `references/guazi-component-usage.md`: apply component-level rules

### Component Rules

- `references/guazi-navbar-component.md`: apply detailed NavBar selection and title-bar rules
- `references/guazi-input-component.md`: apply detailed Input selection and form-field rules
- `references/guazi-upload-component.md`: apply detailed Upload selection and material-upload rules
- `references/guazi-tabs-component.md`: apply detailed Tabs selection and top-switching rules
- `references/guazi-search-component.md`: apply detailed Search selection and search-row rules
- `references/guazi-button-component.md`: apply detailed Button sizing and action-hierarchy rules
- `references/guazi-tag-component.md`: apply detailed Tag selection and status-chip rules
- `references/guazi-dialog-component.md`: apply detailed Dialog selection and popup rules
- `references/guazi-toast-component.md`: apply detailed Toast selection and lightweight feedback rules
- `references/guazi-loading-component.md`: apply detailed Loading selection and waiting-state rules

### Page Patterns

- `references/guazi-list-page-layout.md`: apply when the page is primarily a list page
- `references/guazi-standard-list-examples.md`: use concrete Guazi list-page patterns extracted from production-style samples
- `references/guazi-detail-page-layout.md`: apply when the page is primarily a detail page
- `references/guazi-standard-detail-examples.md`: use concrete Guazi detail-page patterns extracted from production-style samples
- `references/guazi-form-page-layout.md`: apply when the page is primarily a form page

If the page is hybrid, select the dominant pattern first and then layer the secondary pattern only for the matching section.

## Required Outcome

Every run of this skill should aim to produce both:

- a usable frontend page in code
- a corresponding Figma page

Every generated page should satisfy this rule order:

1. Base visual language from `$guazi-design-style-guide`
2. Component usage rules from `references/guazi-component-usage.md`
3. Page-type scaffold rules from the routed page-pattern reference
4. Business-specific requirement details from the user

The Figma page created from code must follow these rules:

- Use a `375px`-wide frame as the page carrier
- Reuse Guazi component-library instances whenever equivalent components exist
- Only hand-build containers or layout wrappers when the library has no suitable compound component

## Reading Order

When context is tight, read in this order:

1. `references/guazi-input-source-routing.md`
2. `references/guazi-page-type-routing.md`
3. `references/guazi-component-usage.md`
4. only the component references actually triggered by the page
5. one dominant page-pattern reference
6. the nearest standard example file if the page is list or detail heavy

## Workflow

### 1. Understand the requirement

- First identify the input source type through `references/guazi-input-source-routing.md`
- If the input includes a requirement document, treat the requirement document as the primary source for layout constraints
- Identify page type, major sections, important actions, and critical states
- Explicitly classify the page as one of: list page, detail page, form page, or hybrid page
- Translate vague product language into concrete UI modules before coding
- If the user gives only prose, create a section list first
- If the input is a prototype image or screenshot, always analyze the prototype structure first (page shell, section order, card hierarchy, action hierarchy), then generate the page with Guazi design rules instead of copying raw visual styles
- If the user gives prototype HTML, extract DOM structure and interaction grouping first, then normalize it into Guazi layout and components
- Load `references/guazi-page-type-routing.md` to determine the dominant page type
- When multiple inputs are provided together, resolve them in this order:
  - business rules -> requirement document
  - layout structure -> prototype image or prototype HTML
  - final visual language -> Guazi rules and component library
- For list pages, also extract:
  - search/filter controls
  - result summary text
  - item-card information hierarchy
  - per-item action priority
  - empty/loading/error states
- For requirement-document inputs, also extract explicitly:
  - layout specifications and section ordering requirements
  - interaction requirements from the "交互说明" or equivalent interaction section

Typical output of this step:

- input source type
- page title
- page type
- section list
- CTA list
- state list

### 2. Route to the correct rule stack

- Always apply `$guazi-design-style-guide` as the global authority
- Always apply `references/guazi-component-usage.md` before placing controls
- When the page has a title bar, also apply `references/guazi-navbar-component.md`
- When the page has input fields, also apply `references/guazi-input-component.md`
- When the page has image or file upload, also apply `references/guazi-upload-component.md`
- When the page has category switching or section switching, also apply `references/guazi-tabs-component.md`
- When the page has keyword search or searchable filtering, also apply `references/guazi-search-component.md`
- When the page has explicit CTAs or action rows, also apply `references/guazi-button-component.md`
- When the page has status chips, metadata tags, or selectable filter chips, also apply `references/guazi-tag-component.md`
- When the page has confirm popups, feedback popups, input popups, or image-led overlays, also apply `references/guazi-dialog-component.md`
- When the page has lightweight success/error/warning/loading feedback, also apply `references/guazi-toast-component.md`
- When the page has inline loading, section loading, page loading, submit waiting, or async placeholder states, also apply `references/guazi-loading-component.md`
- Then apply exactly one dominant page-pattern reference:
  - list page -> `references/guazi-list-page-layout.md`
  - detail page -> `references/guazi-detail-page-layout.md`
  - form page -> `references/guazi-form-page-layout.md`
- When the page is a list page, also use `references/guazi-standard-list-examples.md` to choose the nearest concrete scaffold
- When the page is a detail page, also use `references/guazi-standard-detail-examples.md` to choose the nearest concrete scaffold
- If the page is hybrid, choose the dominant pattern for the shell and use the secondary pattern only inside the relevant module
- Do not invent a page scaffold before choosing the page type

### 3. Implement the frontend page

- Build the page in the local codebase first
- Implement interaction behavior described in the requirement document, not only static layout
- Reuse local frontend components whenever possible
- Use `$guazi-design-style-guide` to enforce Guazi spacing, typography, radius, color, header, and card rules
- Use `references/guazi-component-usage.md` to choose the right Guazi component for each module
- If the page type is a list page, apply `references/guazi-list-page-layout.md` after the base guide and component rules so list density, search layout, card structure, and CTA placement follow the Guazi list pattern
- If the page type is a detail page, apply `references/guazi-detail-page-layout.md` for summary cards, timeline/section ordering, sticky actions, and evidence blocks
- If the page type is a form page, apply `references/guazi-form-page-layout.md` for field grouping, required indicators, helper text, upload areas, and submit behavior
- Ensure the page can be previewed locally before any Figma sync step

### 4. Verify the frontend page

- Make sure the page is reachable in the local app
- After page generation, automatically start local preview (default `npm run dev`) unless the user explicitly opts out
- Provide the local preview URL in the hand-off so the page can be checked immediately
- Validate layout on the current viewport
- Confirm the implementation matches the Guazi style guide before syncing to Figma
- Confirm the controls match the component-usage reference before syncing to Figma
- For list pages, confirm the search/filter area, result summary row, list card spacing, and primary-vs-secondary action hierarchy all match the list-page layout spec
- For detail pages, confirm the info hierarchy, evidence order, and sticky action area match the detail-page layout spec
- For form pages, confirm field grouping, label rhythm, validation affordances, and button hierarchy match the form-page layout spec

### 5. Send the page to Figma

For first-pass webpage capture, use the local-page capture flow from the Figma tools. This gives a fast visual baseline.

- If no target file exists yet, create or capture into a new Figma file
- If a target file already exists, capture into that file
- Do not stop after the HTML capture if the user requires component-library usage in Figma

### 6. Build the componentized Figma version

After capture, create or update a second Figma frame that uses Guazi library instances.

Mandatory rules:

- The componentized frame must be `375px` wide
- The frame should live in the target Figma file alongside the captured version if both are useful
- When writing to Figma, prefer layout-driven construction (Auto Layout first) over absolute positioning
- Keep spacing, alignment, and section flow controlled by layout containers whenever possible
- Use published Guazi instances for things like:
  - `NavBar 导航栏 - H5`
  - `NavBar 导航栏 - mini program小程序`
  - `Button 按钮`
  - `Tabs 选项卡`
  - `Input 输入框`
  - `Switch 开关`
  - `Avatar 头像`
  - `item/tag`
- If a required compound component does not exist, compose it manually using Guazi tokens and the nearest published primitives

### 7. Validate the Figma result

- Check the resulting Figma node with `get_screenshot`
- If screenshot output looks stale, verify instance text and properties directly with `use_figma`
- Keep the componentized frame only if it actually uses library instances for the components that matter

## Practical Rules

- Code is the source of truth for functional behavior; Figma is the synchronized design artifact
- Do not treat HTML capture as equivalent to a design-system implementation
- A requirement document is the source of truth for business rules, fields, states, and logic
- A requirement document is also the source of truth for layout specifications and interaction behavior when those sections are provided
- A prototype image or Figma source is the main hint for section ordering and visual hierarchy
- For prototype-image inputs, structure comes from the prototype, but styling and component choice must follow Guazi design rules
- A prototype HTML file is a structural input, not a styling source of truth
- The base Guazi style guide remains the global style authority
- Component-level choices must come from `references/guazi-component-usage.md` before local invention
- Page-pattern rules only override the page scaffold and section rhythm for their own page type
- If the user asks for "放到 Figma" and also cares about component-library correctness, do both:
  - capture the live page
  - build the componentized 375px frame
- Prefer H5 navbar instances for web pages unless the user explicitly wants mini-program behavior
- Keep the Figma write process incremental: wrapper frame first, then section by section
- In Figma, prefer nested layout containers for rows/columns/action bars and avoid pixel-fixed absolute placement unless unavoidable
- When the requirement is ambiguous, make the page-type decision explicitly in the response before implementation

## Deliverables Checklist

Before finishing, confirm all of the following:

- frontend page exists in code
- local preview was started automatically (unless user opted out)
- page is previewable locally
- page type was identified
- requirement-document layout specifications were applied (when provided)
- requirement-document interaction behavior was implemented (when provided)
- design rules were applied through `$guazi-design-style-guide`
- component rules were applied through `references/guazi-component-usage.md`
- page was sent to Figma
- a `375px` componentized frame exists in Figma
- Guazi library instances were used where available

## Resources

- `references/guazi-page-design-reference.md`: a compact execution checklist for requirement parsing, code delivery, and Figma componentized sync.
- `references/guazi-input-source-routing.md`: input-source identification and conflict-resolution rules for requirement docs, prototype images, and prototype HTML files.
- `references/guazi-page-type-routing.md`: page-type identification heuristics and routing rules.
- `references/guazi-component-usage.md`: component selection, priority, and usage guidance.
- `references/guazi-navbar-component.md`: detailed navbar variants and page-title usage rules.
- `references/guazi-input-component.md`: detailed input variants and form-field usage rules.
- `references/guazi-upload-component.md`: detailed upload variants and material-upload usage rules.
- `references/guazi-tabs-component.md`: detailed tabs variants and page-switching usage rules.
- `references/guazi-search-component.md`: detailed search variants and search-row usage rules.
- `references/guazi-button-component.md`: detailed button sizes, list-card action rules, and CTA hierarchy rules.
- `references/guazi-tag-component.md`: detailed tag variants and status-chip usage rules.
- `references/guazi-dialog-component.md`: detailed dialog variants and popup usage rules.
- `references/guazi-toast-component.md`: detailed toast variants and lightweight feedback usage rules.
- `references/guazi-loading-component.md`: detailed loading variants and waiting-state usage rules.
- `references/guazi-list-page-layout.md`: list-page structure rules derived from the Guazi list-page pattern in Figma. Use this on top of the base Guazi style guide whenever the page is primarily a searchable or filterable list.
- `references/guazi-standard-list-examples.md`: concrete list-page examples extracted from standard Guazi list pages.
- `references/guazi-detail-page-layout.md`: detail-page structure rules for read-heavy and action-driven transactional pages.
- `references/guazi-standard-detail-examples.md`: concrete detail-page examples extracted from standard Guazi detail pages.
- `references/guazi-form-page-layout.md`: form-page structure rules for create/edit/apply/submit flows.
