# Guazi Button Component

This reference is distilled from the Guazi Design button documentation page:

- file: `Guazi Design`
- page node: `24317:5233`
- main component set: `26511:4342`

Use this file together with:

- `$guazi-design-style-guide`
- `references/guazi-component-usage.md`

## 1. Component Families

The button documentation page includes these practical button families:

- Basic Button 基础按钮
- Icon Button 图标按钮
- Ghost Button 幽灵按钮
- Block Button 通栏按钮
- Button Group 组合按钮

For the main reusable component set, the core implementation axes are:

- `variant`: `base | outline | text | ghost`
- `theme`: `primary | light | default | text`
- `size`: `large | medium | small | extraSmall`
- `shape`: `rectangle | square`
- `prefixIcon`: `true | false`
- `suffixIcon`: `true | false`
- `singleIcon`: `true | false`
- `press`: `true | false`
- `disabled`: `true | false`

Practical rule:

- treat `Block` and `Button Group` as layout patterns built from the same button family
- treat `Round` and `Circle` as presentation examples on the page, but keep `rectangle` and `square` as the primary code-facing shape model unless the design explicitly requires otherwise

## 2. Visual Rules

- default control radius: `4px`
- primary brand action:
  - normal: `#00AE78`
  - press: `#00875D`
  - focus/light assist: `#CCEFE4`
- light button surface: `#EBF9F5`
- default neutral support:
  - fill: `#F3F5F7`
  - border in lighter neutral cases: `#D8DDE6`
- primary text on filled brand button: `#FFFFFF`
- disabled text/icon for button content: `#BAC2C9`

## 3. Size, Text, And Icon Rules

### `large`

Use for:

- page-primary CTA
- form bottom submit action
- high-emphasis confirm action

Observed rules:

- visual height: `44px`
- text token: `16 / 22`, semibold
- icon size: `22px`
- square icon button: `44 x 44`

### `medium`

Use for:

- ordinary page actions
- popup footer buttons
- section-level action rows

Observed rules:

- visual height: `40px`
- text token: `14 / 20`, semibold
- icon size: `20px`
- square icon button: `40 x 40`

### `small`

Use for:

- compact toolbar actions
- card actions with moderate density
- narrow inline action groups

Observed rules:

- visual height: `32px`
- text token: `14 / 20`, semibold
- icon size: `18px`
- square icon button: `32 x 32`

### `extraSmall`

Use for:

- dense list-card actions
- list trailing operation rows
- tightly packed operational controls

Observed rules:

- visual height: `28px`
- text token: `12 / 18`, semibold
- icon size: `16px`
- square icon button: `28 x 28`

Practical rule:

- if the user says "最小号按钮", map it to `extraSmall`, not `small`

## 4. Icon Rules

- `prefixIcon` is used to express action type or object
- `suffixIcon` is used to express forward direction, disclosure, or next-step meaning
- `singleIcon` is the icon-only pattern and should map to `shape=square`
- icon size scales with button size:
  - `large`: `22px`
  - `medium`: `20px`
  - `small`: `18px`
  - `extraSmall`: `16px`

Accessibility rule:

- single-icon buttons must expose `aria-label` or equivalent tooltip/assistive text

## 5. State Rules

The button page explicitly demonstrates:

- normal
- press / active
- disabled

Generation rules:

- do not model `press` as a business prop unless the design system layer truly needs it
- in product code, prefer hover / active pseudo-states or framework interaction states
- `disabled` must remain a business-controlled boolean

## 6. Action Hierarchy

In horizontal action rows:

- primary CTA must sit on the far right
- secondary and helper actions stay on the left
- keep action count small; `3` is a good default maximum for list cards

Example list-card order:

- `修改图片`
- `下架`
- `改价`

Where `改价` is the primary CTA and must stay on the far right.

## 7. Layout Patterns

### Block Button

Use for:

- bottom-of-page primary actions
- form submit areas
- full-width transactional CTA rows

Rule:

- treat block as width behavior, not a separate color family

### Button Group

Observed rule:

- grouped segmented actions on the page use `28px` height

Use for:

- segmented compact choices
- tightly grouped action states

### Dense List-Button Pattern

Use for:

- card tail actions
- operational list items

Rules:

- default to `extraSmall`
- keep `8px` gap between buttons
- do not mix heights in the same row
- shorten copy before compressing the button below its intended size

## 8. Label Rules

The button documentation page explicitly recommends:

- preferred label length: `2~6` Chinese characters
- ordinary upper bound: no more than `8` Chinese characters
- prefer `verb + object`

Examples:

- good: `提交审核`
- good: `查看记录`
- weak: `立即操作`
- weak: `立即查看`

## 9. Usage Mapping

Recommended page mapping:

- form page bottom CTA -> `base`, usually `large`
- dialog footer pair -> `base + outline`, usually `medium`
- list-card tail actions -> `outline / text / outline + primary`, usually `extraSmall`
- toolbar actions -> `text` or `outline`, usually `small`
- image or dark-surface overlay action -> `ghost`

## 10. Generation Rules

When generating pages:

- use `extraSmall` buttons in dense list cards by default
- use `small` when the row is compact but still needs more breathing room than list-tail operations
- use `medium` for ordinary page actions by default
- use `large` for page-primary CTA and submit-heavy form flows
- if the button is icon-only, map it to `shape=square`
- if the environment lacks a full design-system button implementation, preserve this size hierarchy and visual ordering in the local button wrapper
