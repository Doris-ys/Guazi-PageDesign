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
3. `客户详情`

Practical classification:

- `交易证明` is a document / proof detail page
- `工具页` is an operational tool detail page with hero media, key metrics, section tabs, and a bottom action bar
- `客户详情` is a CRM / relationship detail page with summary header, focus-object card, task feed, and mixed bottom actions

## 2. Shared Detail-Shell Pattern

Across the detail pages, the common scaffold is:

1. status bar
2. `NavBar 导航栏 - H5`
3. top summary area
4. grouped white information sections
5. bottom action area

Rule:

- For Guazi transactional detail pages, treat this as the default shell before inventing new structures
- When the object is a customer, merchant, or clue rather than a document, the summary area can be a light header block instead of a separate white card

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

## 5. CRM / Relationship Detail Pattern

Source sample:

- file: `G38oVi0JYCVmv4G6GWkSSo`
- node: `88:1197`
- page name: `订单列表 - 零售订单`
- screen title: `客户详情`

Use when the page's primary job is to help the user understand one person or merchant, review the current focus object, and continue relationship follow-up.

### Structure

Observed pattern:

1. navbar
2. customer identity header with name, ID, intent tags, and business count
3. current focus car-source card
4. recent activity fact rows
5. top tabs with record counts
6. event / to-do feed cards
7. sticky bottom mixed action bar

### Summary header

Observed pattern:

- the top summary is not a heavy white card
- name and ID are the first scan target
- intent or behavior tags sit directly below the name
- a right-aligned count gives immediate business context
- the current car source is embedded as a compact light-gray card under the identity block

Rule:

- Use this pattern for `客户详情`, `线索详情`, `商机详情`, `跟进对象详情` and similar pages
- Keep the identity block compact and information-dense instead of decorative
- Show the current focus object directly under the identity so the operator knows what the next actions are about

### Activity fact rows

Observed pattern:

- recent behavioral facts are shown as short one-line rows
- one label plus several inline facts are separated by thin dividers
- the copy stays factual and compact

Rule:

- Use inline fact rows for `买家活动`, `上次活跃`, `首次建联`, `客户备注` and similar overview content
- Prefer this over stacking many standalone mini-cards
- Keep row height stable and use tertiary labels with darker values

### Record feed cards

Observed pattern:

- each card shows a status chip or icon on the left and time on the right
- the main business sentence is bolded in the second row
- supporting facts are appended inline rather than split into many rows
- compact `extraSmall` actions are right-aligned at the bottom
- different feed-card types reuse the same outer shell

Rule:

- Use this feed-card pattern for pending actions, negotiation requests, missed calls, appointments, and communication tasks
- Keep the shell stable even when the card content changes by scenario
- Primary action stays at the far right and uses the brand-green light style when it is not a destructive action

### Bottom mixed action bar

Observed pattern:

- the left side contains lightweight icon tools
- the right side contains a secondary button plus a primary button
- the primary action is on the far right

Rule:

- Use this pattern when the operator needs both frequent utility actions and one clear business action
- Keep the utility actions icon-led and short
- Do not turn every action into a full button

## 6. Selection Guidance

When implementing a new Guazi detail page, choose the nearest example first:

- If the page is certificate / proof / statement-like -> start from the `交易证明` pattern
- If the page is a rich operational object page with diagnosis or optimization -> start from the `工具页` pattern
- If the page is centered on one customer or merchant plus follow-up actions -> start from the `客户详情` pattern
- If the page needs one bottom CTA -> lean toward `交易证明`
- If the page needs persistent multi-action tooling -> lean toward `工具页`
- If the page needs tabs plus a to-do / communication feed -> lean toward `客户详情`
