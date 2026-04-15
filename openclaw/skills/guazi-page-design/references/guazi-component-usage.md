# Guazi Component Usage

Use this reference after the base style guide and before any page-level layout reference. Its job is to ensure every page uses the right component for the right job.

## 1. Component Selection Priority

When building a page, choose components in this order:

1. exact Guazi library instance
2. local code component that already matches the Guazi library
3. manual composition from Guazi primitives and tokens

Do not invent a custom component if an equivalent Guazi component already exists.

## 2. Header Components

### `NavBar 导航栏 - H5`

Use for:

- H5 web pages
- list pages
- detail pages
- form pages

Rules:

- keep fixed to the top when the page is operational, transactional, or detail-heavy
- width should align with the full page shell
- do not add shadow by default
- treat this as the default page-title component for H5 pages
- prefer `type=middle` for standard page titles
- prefer `type=left` only when the title is long or the header carries denser context

### `NavBar 导航栏 - mini program小程序`

Use only when the user explicitly requires mini-program behavior or ecosystem constraints.

### `SearchNavBar 搜索导航栏 - H5`

Use for:

- search-first list pages
- temporary search mode pages

Rules:

- use this instead of stacking a normal title bar plus a redundant search bar when search is the dominant action
- use explicit cancel or search-button variants only when the interaction really needs them

For detailed NavBar rules, also read `guazi-navbar-component.md`.

## 3. Action Components

### `Button 按钮`

Use for all explicit actions.

Rules:

- primary CTA: filled Guazi green
- secondary CTA: outline or low-emphasis button
- tertiary action: text action only when hierarchy requires it
- keep action count small; prefer one primary CTA per area
- use compact sizes inside list cards and larger sizes in form or page footers
- use `extraSmall` size for dense list-card actions: `28px` height with `12px` text
- use `small` size for compact toolbar or card actions: `32px` height with `14px` text
- use `medium` size for ordinary page actions: `40px` height with `14px` text
- use `large` size for page-primary CTA: `44px` height with `16px` text

For detailed size and ordering rules, also read `guazi-button-component.md`.

### Action hierarchy

- primary CTA sits far right in horizontal action rows
- destructive actions should never look like primary actions unless the task is truly terminal
- page-bottom action bars should expose at most one primary CTA and one secondary CTA

## 4. Selection Components

### `Tabs 选项卡`

Use for:

- top-level category switching
- clear mutually exclusive datasets

Rules:

- do not use tabs for binary on/off settings
- keep labels short and scannable
- if the view only toggles a single field, prefer radio or segmented selection instead
- prefer `theme=normal` as the default page-level pattern
- prefer `size=small` for dense H5 pages
- use `bottomline=on` for classic top navigation tabs
- use `isometric=true` when peer categories should share equal width
- use `theme=tag` or `theme=card` only when the visual semantics genuinely differ from ordinary page navigation

### `Horizontal Radio` / `Radio 单选`

Use for:

- mutually exclusive choices inside forms
- low-count decisions with 2 to 5 options

Rules:

- use when the user should compare options directly
- do not hide the current choice in a dropdown when all options fit inline

### `Switch 开关`

Use for:

- immediate on/off state changes
- feature toggles with direct effect

Do not use for:

- multi-step submissions
- choices that require confirmation or explanation

## 5. Input Components

### `Input 输入框`

Use for:

- short structured values
- IDs, names, phone numbers, percentages, titles

Rules:

- pair with a visible label in forms
- use placeholder as example guidance, not as the only label
- keep one value type per field
- prefer vertical labeled input as the default H5 form pattern
- use horizontal layout only for denser settings-like rows
- use suffix only when the trailing affordance is truly part of the field interaction
- use tips for format explanation, review guidance, or validation context

### `InputPassword 密码输入框`

Use for:

- passwords
- concealed sensitive strings

Rules:

- keep it visually aligned with the standard Input family
- do not replace ordinary text input with password input just to get an eye icon

### `Search 搜索框`

Use for:

- list-page keyword search
- compact operational search rows

Rules:

- prefer this over a generic input field in the main list search row
- default to a leading search icon and explicit trailing search action in operational lists
- use dropdown search only when the business really needs scoped search
- prefer gray background style as the default dense H5 search pattern

### `Textarea`

Use for:

- explanations
- remarks
- long freeform input

Rules:

- place after structured fields
- provide helper text when the content affects review or approval

### `Upload`

Use for:

- material submission
- screenshots
- certificates
- supporting evidence

Rules:

- always show whether the field is required
- provide example or format guidance when the upload is easy to misunderstand
- group related uploads together under a clear section title
- use single-file upload for one-per-field evidence such as front/back document images
- use multiple-file upload for repeated material of the same category
- preserve upload state clearly: loading, retry, failed, done, disabled
- use image upload tiles as a section-level content area, not as a plain inline button

## 6. Identity And Metadata Components

### `Avatar 头像`

Use for:

- people
- merchant identity blocks
- compact owner or operator summaries

### `Tag 标签`

Use for:

- lightweight metadata
- status chips
- score or level display
- category or business labels

Rules:

- prefer `Tag 标签` as the default tag family for new page generation
- tags should support scanning, not replace core text
- avoid too many colored tags in one row
- keep neutral tags neutral and use green only for emphasis
- prefer `size=small` in dense list cards and `size=medium` near detail titles
- prefer `variant=light` or `lightOutline` on white card surfaces
- use `warning / danger / success` themes only when the business semantics truly match

### `CheckTag 可选标签`

Use for:

- selectable filter chips
- multi-option tag selections
- direct checked / unchecked chip controls

Rules:

- use this instead of `Tag 标签` when the chip itself is interactive
- do not fake selectable filter chips with static tags

### `item/tag`

Use for:

- legacy Guazi card patterns
- reproduction of existing library-composed list/detail examples when they already use `item/tag`

Rules:

- prefer `Tag 标签` for new page generation
- keep `item/tag` only when matching an existing published Guazi composition exactly

### `Dialog 对话框`

Use for:

- confirm / cancel decisions
- short feedback popups
- short input popups
- image-assisted tips or notices

Rules:

- prefer this over hand-built modal cards for new page generation
- use only for short focused interactions, not full-page business flows
- default to horizontal footer actions unless the content or action hierarchy clearly needs vertical buttons

### `Toast 轻提示`

Use for:

- short success feedback
- short error feedback
- warning reminder
- short loading feedback

Rules:

- prefer this for transient result communication instead of dialog
- keep messages short and lightweight
- default to row + icon toast for semantic states
- use column toast only when the feedback needs stronger visual emphasis
- do not use toast as the only carrier for complex validation or decisions

## 7. Card Usage Rules

Cards are layout containers, not standalone semantic controls.

Rules:

- use cards to group related information or form sections
- do not use cards to mimic button affordance
- cards should be white surfaces without gray borders by default
- rely on spacing and section titles before adding extra framing

## 8. Page-Type Mapping Cheatsheet

### List page

- header: `NavBar 导航栏 - H5`
- switching: `Tabs 选项卡` when categories exist
- search/filter: `Input 输入框` plus low-emphasis filter entry
- card tags: `Tag 标签` by default, `item/tag` only for legacy pattern matching
- actions: compact `Button 按钮`

### Detail page

- header: `NavBar 导航栏 - H5`
- summary area: card + optional `Avatar 头像` or status tags
- section actions: `Button 按钮`
- status toggles: `Switch 开关` only when the effect is immediate
- modal confirmation: `Dialog 对话框` when a secondary confirm step is needed
- lightweight result feedback: `Toast 轻提示`

### Form page

- header: `NavBar 导航栏 - H5`
- fields: `Input 输入框`, `InputPassword 密码输入框`, `Textarea`, `Radio`, `Switch`, `Upload`
- footer: two-button action bar when both save and submit exist

## 9. Figma Output Rules

When building the componentized Figma frame:

- use real Guazi library instances for the controls above whenever available
- keep the outer carrier frame at `375px`
- hand-build only the layout shells and compound wrappers that do not exist in the library

For detailed input rules, also read `guazi-input-component.md`.
For detailed upload rules, also read `guazi-upload-component.md`.
For detailed Tabs rules, also read `guazi-tabs-component.md`.
For detailed Search rules, also read `guazi-search-component.md`.
For detailed Tag rules, also read `guazi-tag-component.md`.
For detailed Dialog rules, also read `guazi-dialog-component.md`.
For detailed Toast rules, also read `guazi-toast-component.md`.
