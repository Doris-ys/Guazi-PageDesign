# Guazi List Page Layout

This reference defines the default Guazi list-page scaffold. It is based on the Guazi list-page pattern in Figma:

- File: `Profile Page - Guazi Design`
- Node: `88:391`

Also use `guazi-standard-list-examples.md` for more concrete production-style list patterns extracted from:

- file: `车优多-零售`
- node: `2:3`

Use this reference only for list pages. It layers on top of `$guazi-design-style-guide`, which remains the source of truth for shared tokens such as color, typography, radius, and generic page behavior.

## 1. When To Apply

Apply this layout when the page's primary job is to help the user scan, search, filter, or act on repeated records, for example:

- merchant lists
- dealer lists
- vehicle lists
- task lists
- record pickers

Do not use this list scaffold for detail pages or form-first pages unless the list is the dominant module.

## 2. Rule Priority

For list pages, follow the rules in this order:

1. `$guazi-design-style-guide` for base Guazi visual language
2. This document for list-page scaffold and density
3. The page requirement for business-specific sections and actions

If this document conflicts with the generic H5 card defaults, this document wins for list-page rows, search areas, and list cards.

## 3. Page Scaffold

The default list-page order is:

1. top navigation or title bar
2. optional category tabs
3. search and filter row
4. result summary row
5. repeated list cards
6. optional bottom navigation when the requirement is a tool/home channel page

Implementation intent:

- keep the scaffold vertically stacked and easy to scan
- allow the page body to scroll while the global shell remains visually stable
- avoid decorative hero sections before the search area

For operational order-style lists, the concrete first-screen scaffold can be:

1. top navigation or title bar
2. category tabs
3. search field
4. quick filter chip row
5. repeated cards

## 4. Header, Tabs, And Search Area

### Header

- Use the Guazi page-header rule from `$guazi-design-style-guide`
- For H5 list pages, prefer a fixed top bar when the page is a top-level operational page
- In Figma, use a `375px` frame for the componentized version

### Tabs

- If the list is split into clear categories, place `Tabs 选项卡` directly under the header
- Tabs should span full width and sit on a white surface
- Active tab uses the Guazi green emphasis and a short bottom track
- Prefer `theme=normal`, `size=small`, `bottomline=on`
- Use `isometric=true` when the categories are peers such as `全部 / 进行中 / 已完成`
- If the row behaves more like lightweight filter chips than page sections, consider `theme=tag` instead of the default line tabs

### Search + Filter Row

- Place the search row immediately below tabs or header
- Use a white row container with approximately `10px` horizontal padding and `8px` vertical padding
- The search field should be the dominant element in the row
- Search field styling should be compact and dense:
  - prefer the Guazi `Search 搜索框` component
  - light gray fill by default
  - `4px` radius
  - icon + placeholder/value text
- Filter entry, if present, sits on the trailing side as a low-emphasis text action with an icon
- In order-style lists, a quick filter button row may appear below the search bar when the business has a few high-value shortcut statuses
- Prefer a dedicated search component over a plain input shell for the first-row list search

## 5. Result Summary Row

- Place a compact summary row below the search area and above the first card
- Recommended content is result count or status summary, for example `共 23 条数据`
- Use small secondary text (`12px` scale, Guazi gray)
- The summary row can sit on a subtle tinted background if the page uses a gentle top gradient

## 6. List Container Spacing

- Keep `10px` page-side gutters for the list content
- Keep `10px` vertical gap between cards
- Do not add extra card borders or shadows just to separate records
- If the page uses a soft background tint or gradient behind the first screen, keep it subtle and non-interactive

## 7. List Card Structure

Default list cards should use a compact information hierarchy:

1. merchant or record title row
2. supporting location or subtitle row
3. tags row or wrapped tag block
4. one or more key-value information rows
5. optional metrics rows
6. trailing action row

For order-style operational lists, a more concrete pattern is:

1. order or record ID row
2. status on the top-right
3. thumbnail + title + core meta
4. tag row
5. optional helper strip
6. compact action row

For finance/account lists, a more concrete pattern is:

1. section marker title
2. repeated key-value rows
3. emphasized amount row

Card styling defaults:

- white surface
- `8px` radius
- no gray border
- no visible elevation
- `14px` inner padding

Optional enhancement:

- a very soft green-tinted top gradient can be used inside the card head area to hint importance, but it should not read as a banner

## 8. Title And Metadata Rules

### Title Row

- Title stays left and should be the strongest text in the card
- Recommended title styling is compact semibold or medium around `15px / 22px`
- A compact level badge may appear beside the title
- Low-emphasis detail entry such as `查看详情` belongs on the right, not in the primary action row

### Address / Subtitle Row

- Use icon + text + optional chevron
- Keep this row visually lighter than the title
- Long text should truncate before it breaks the card rhythm

### Tags

- Tags should wrap naturally on narrow screens
- Default list tags are dense neutral chips:
  - `#F5F6F7` background
  - Guazi gray text
  - small radius such as `2px`
  - compact horizontal and vertical padding
- Metric chips such as score or level may use Guazi green values inside otherwise neutral chips

## 9. Key-Value Information Rows

- Prefer a two-column scan pattern when the content allows it
- Labels should use small secondary text and keep a stable width
- Values should use darker text and remain easy to compare across cards
- For dense operational metrics, use inline value groups separated by spacing or subtle dividers instead of large nested blocks

Good examples:

- `商户ID / 城市`
- `BD姓名 / 上次拜访时间`
- `本月目标`
- `车源结构`
- `友商对比`

## 10. Per-Item Actions

- Keep the primary action inside the card footer row
- Place the most important CTA on the far right
- Supporting actions stay to the left of the primary CTA
- Keep the number of actions small; `3` is a good default maximum

Dense list-button pattern:

- compact button height around `28px`
- `4px` radius
- `8px` gap between buttons
- primary CTA uses filled Guazi green
- secondary CTA uses outline Guazi green on white

Example hierarchy:

- `车辆列表`
- `新建拜访`
- `去拜访` ← primary

In order-style lists, helper strips and action rows may coexist. In that case:

- keep the helper strip above the action row
- keep the action row compact and stable
- do not merge warning text directly into the action buttons

## 11. Responsive And Behavioral Rules

- In code, allow the list width to expand responsively while preserving the Guazi spacing rhythm
- In Figma componentized output, still use a `375px` frame carrier
- Preserve stable action order across all cards
- Keep search, tabs, and result summary visible before the user enters the list body
- Provide explicit empty states under the search/filter area when no results match

## 12. Figma Component Reuse Guidance

When building the componentized Figma version of a list page, prefer these Guazi instances when available:

- `NavBar 导航栏 - H5`
- `Tabs 选项卡`
- `Button 按钮`
- `item/tag`

Hand-build only the card container and information rows that do not have a direct published equivalent.
