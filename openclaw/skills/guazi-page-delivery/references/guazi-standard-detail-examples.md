# Guazi Standard Detail Examples

This reference is distilled from the Figma file:

- file: `G38oVi0JYCVmv4G6GWkSSo`
- page node: `32:9478`
- file name: `车优多-零售`

The file contains multiple standard detail-style samples. Use them as concrete examples when implementing Guazi detail pages.

## 1. Sample Set Overview

Observed sample pages:

1. `交易证明`
2. `工具页`

Practical classification:

- `交易证明` is a document / proof detail page
- `工具页` is an operational tool detail page with hero media, key metrics, section tabs, and a bottom action bar

## 2. Shared Detail-Shell Pattern

Across the detail pages, the common scaffold is:

1. status bar
2. `NavBar 导航栏 - H5`
3. top summary area
4. grouped white information sections
5. bottom action area

Rule:

- For Guazi transactional detail pages, treat this as the default shell before inventing new structures

## 3. Proof / Document Detail Pattern

Use when the page's primary job is to show official-looking record details, certificates, transaction proofs, or downloadable evidence.

### Structure

Observed pattern:

1. navbar
2. stacked white cards with section titles
3. repeated key-value rows inside each card
4. sticky bottom CTA

### Card pattern

Observed section-card behavior:

- each card has a clear section title
- dense key-value rows
- values are often right-aligned for scanability
- little or no decorative chrome

Rule:

- Use this pattern for finance proofs, transaction certificates, statement-style detail pages, and read-only operational records
- Keep the content card-driven and row-based instead of mixing too much media or segmented switching

### Bottom action

Observed pattern:

- single strong CTA at the bottom

Rule:

- Use one clear export / confirm / download CTA when the page's next step is singular and obvious

## 4. Operational Tool Detail Pattern

Use when the page's primary job is to help the user understand one object and then optimize, diagnose, or operate on it.

### Structure

Observed pattern:

1. large visual summary or hero media
2. strong price / metric strip
3. title + meta + source info
4. tags or lightweight status chips
5. horizontal tabs for peer content sections
6. task or suggestion cards
7. bottom operation bar

### Hero area

Observed pattern:

- large image at top
- lightweight mode switch over the media
- metric summary attached directly below

Rule:

- Use a hero area only when the object itself is visually important and the page benefits from immediate visual recognition
- Do not add hero media to ordinary proof/detail pages

### Section switching

Observed pattern:

- tabs are used to split peer sections such as base info, diagnosis, intent, activities

Rule:

- Use tabs when the page has clearly parallel content domains
- Keep tabs close to the content they switch

### Suggestion cards

Observed pattern:

- repeated action-oriented cards
- ranking/order cue on the left
- short explanation text
- compact CTA on the right

Rule:

- Use this pattern for diagnosis, opportunities, and optimization recommendations
- Keep each suggestion card focused on one issue and one next action

### Bottom tool bar

Observed pattern:

- multi-action bottom bar with lightweight tools plus one stronger primary CTA

Rule:

- Use this pattern for tool pages where the user may need several operational actions at any time
- Keep one action visually primary and the rest lightweight

## 5. Selection Guidance

When implementing a new Guazi detail page, choose the nearest example first:

- If the page is certificate / proof / statement-like -> start from the `交易证明` pattern
- If the page is a rich operational object page with diagnosis or optimization -> start from the `工具页` pattern
- If the page needs one bottom CTA -> lean toward `交易证明`
- If the page needs persistent multi-action tooling -> lean toward `工具页`
