# Guazi Tag Component

Use this reference when the page needs status chips, metadata labels, business tags, or removable tags.

This reference is distilled from the Figma library:

- file: `IlDoKwM2KnSOdvFyFskkP6`
- page node: `24386:5275`
- component set node: `26737:7637`
- file name: `Guazi Design`

## 1. Components In Scope

There are three related tag-like components in the Guazi library:

1. `Tag 标签`
2. `CheckTag 可选标签`
3. `item/tag`

Practical rule:

- use `Tag 标签` for ordinary status and metadata display
- use `CheckTag 可选标签` for selectable filter chips
- use `item/tag` only when matching an existing legacy card pattern or an already-published Guazi list/detail composition

## 2. `Tag 标签` Variant Axes

Observed directly from the `Tag 标签` component set:

- `variant`: `dark | light | outline | lightOutline`
- `theme`: `default | primary | warning | danger | success | Sales`
- `size`: `large | medium | small`
- `shape`: `square`
- `prefixIcon`: `true | false`
- `closable`: `true | false`
- `disabled`: the page explicitly documents disabled examples; treat it as a supported state even when many sample nodes are shown in enabled form

Observed heights:

- `large`: `20px`
- `medium`: `18px`
- `small`: `16px`

The system radius reference still applies:

- default tag radius: `4px`

## 3. Variant Meaning

### `variant=dark`

Use for:

- stronger status emphasis
- darker filled semantic tags
- cases where the tag should stand out clearly in a dense card

Rule:

- do not use `dark` as the default metadata tag style in ordinary white cards

### `variant=light`

Use for:

- default page-level status tags
- soft semantic emphasis
- lightweight labels inside cards

Rule:

- this is the safest default for H5 detail and list cards

### `variant=outline`

Use for:

- lower-emphasis semantic tags
- outlined chips that still carry status meaning

Rule:

- prefer this when the tag should read as present but not dominant

### `variant=lightOutline`

Use for:

- very light page metadata
- low-noise supporting labels
- dense tag rows in read-heavy cards

Rule:

- prefer this over `outline` when the page already has enough visual emphasis elsewhere

## 4. Theme Meaning

### `theme=default`

Use for:

- neutral metadata
- business attributes that are informative but not status-critical
- card tags such as category, source, type, or lightweight labels

Default rule:

- neutral tags should usually start here

### `theme=primary`

Use for:

- positive emphasis tied to the Guazi main accent
- current focus state
- promoted business labels when the design wants green emphasis

Rule:

- do not use `primary` for every tag in a row; keep one highlighted idea at most

### `theme=warning`

Use for:

- caution states
- pending risk
- process reminders that need attention but are not terminal

### `theme=danger`

Use for:

- abnormal or failed states
- rejected or expired conditions
- high-risk business warnings

### `theme=success`

Use for:

- completed or successful states
- confirmed good conditions

### `theme=Sales`

Use for:

- explicit sales-domain or business-domain labels when the source design already uses this business theme

Rule:

- do not treat `Sales` as a general-purpose accent theme

## 5. Size Selection

### `small`

Use for:

- dense list cards
- wrapped metadata rows
- high-volume tag groups

Default rule:

- this is the primary default for operational H5 lists

### `medium`

Use for:

- ordinary detail-card tags
- status chips near titles
- moderate-emphasis metadata

Default rule:

- this is the safest default for detail pages

### `large`

Use for:

- very important status labels
- sparse summary areas

Rule:

- use sparingly; most transactional pages do not need large tags

## 6. Prefix Icon And Closable

### `prefixIcon=true`

Use for:

- states where the icon adds real semantic value
- tags that need a stable recognition cue

Rules:

- do not add icons just for decoration
- keep iconized tags sparse in one row

### `closable=true`

Use for:

- removable user selections
- editable tag collections

Do not use for:

- read-only status tags
- backend-driven business states

## 7. `CheckTag 可选标签` vs `Tag 标签`

Use `CheckTag 可选标签` when the tag itself is a selectable control.

Signals:

- checked / unchecked state
- filter chip behavior
- category selection
- user can toggle the chip directly

Use `Tag 标签` when the tag is read-only display.

Signals:

- status label
- metadata chip
- category display without direct selection

## 8. `item/tag` vs `Tag 标签`

Practical migration rule:

- prefer `Tag 标签` for new page generation
- keep `item/tag` when reproducing an existing Guazi production pattern that already uses it

Reason:

- `Tag 标签` is the more explicit and modern tag family with clearer semantic axes
- `item/tag` still appears in some existing composed list/detail patterns

## 9. Page-Level Usage Rules

### List page

- default metadata row: `Tag 标签`, `theme=default`, `variant=lightOutline` or `light`, `size=small`
- critical per-item status: one stronger semantic tag only
- let tags wrap naturally on narrow screens

### Detail page

- title-adjacent status: `Tag 标签`, usually `size=medium`
- supporting metadata row: neutral tags first, one semantic tag if needed

### Form page

- prefer helper text over decorative tags
- use tags only when they clarify immutable state, category, or preselected business context

## 10. Figma Output Rules

When building the componentized Figma frame:

- prefer the real `Tag 标签` instance for status and metadata chips
- prefer `CheckTag 可选标签` for selectable filter rows
- avoid rebuilding tags from text + rectangle unless no equivalent library instance exists
