# Guazi Detail Page Layout

Use this reference for detail-heavy pages whose primary job is to help the user understand one object and take the next action.

Also use `guazi-standard-detail-examples.md` for more concrete production-style detail patterns extracted from:

- file: `车优多-零售`
- node: `32:9478`

## 1. Page Goal

A detail page should answer three questions in order:

1. What is this object?
2. What is its current status?
3. What should the user do next?

## 2. Default Scaffold

The default detail-page order is:

1. fixed top navbar
2. summary card
3. key status or progress section
4. grouped information cards
5. evidence or attachment section
6. sticky bottom action bar when an important next step exists

Two concrete detail scaffolds are especially useful:

### Proof / document detail

1. fixed top navbar
2. stacked white info cards
3. dense key-value rows
4. single sticky bottom CTA

### Operational tool detail

1. fixed top navbar
2. hero media or visual summary
3. price / metric strip
4. title and metadata block
5. tabs for peer sections
6. repeated suggestion or operation cards
7. multi-action bottom tool bar

## 3. Summary Card

The first card should establish identity quickly.

Recommended content:

- title or record name
- ID or code
- primary status
- one or two key metrics
- optional tag row

Rules:

- keep the title strongest
- place status near the title, not buried in later sections
- avoid overly tall hero cards

For proof/detail pages, the first card may be a purely informational summary card with dense rows.
For operational tool pages, the summary may be split between hero media, metric strip, and title/meta block.

## 4. Section Order

Order sections by decision value, not by backend field order.

Recommended order:

1. status / progress
2. high-value business facts
3. operational metadata
4. attachments or evidence
5. extended remarks or history

If the detail content is split into peer sections such as `基本信息 / 材料 / 记录`, tabs may be used near the top of the content area. In that case:

- prefer `Tabs 选项卡` with `theme=normal`
- keep the tab bar directly attached to the switched content area
- avoid tabs if a simple vertical section stack is clearer

## 5. Information Cards

Use compact grouped cards.

Rules:

- keep `10px` outer gutter and `10px` card gap from the global Guazi rule
- use `14px` card inner padding
- prefer two-column key-value layouts when fields are comparable
- long-form content should be separated from dense metadata

## 6. Status And Timeline Areas

Use when the record changes over time.

Rules:

- show current state first
- keep completed vs pending visually distinct
- do not force the user to infer status from color alone
- if there is a next required action, place it close to the status area

## 7. Evidence / Attachment Areas

Use for screenshots, uploaded files, certificates, and downloadable materials.

Rules:

- group by material type
- show whether the evidence is uploaded, missing, approved, or rejected
- place download actions close to the material entry
- if the page has many file rows, keep the row pattern stable

For proof/detail pages, evidence often appears as row-based factual sections rather than thumbnail galleries.
For operational tool pages, evidence may be richer and mixed with tabs or suggestion modules.

## 8. Sticky Bottom Actions

Use when the page has a clear next step.

Rules:

- keep one primary CTA
- add one secondary CTA only when needed
- keep the bar stable and easy to reach
- avoid placing primary actions deep inside the scroll body if the action should always be available

If the page is a proof/detail page, prefer a single strong bottom CTA.
If the page is an operational tool page, a multi-action bottom bar may be appropriate, but only one action should read as primary.

## 9. Common Detail-Page States

Detail pages should consider:

- loading
- empty or missing record
- rejected or abnormal status
- attachment missing
- success after action

## 10. Figma Reuse Guidance

Prefer:

- `NavBar 导航栏 - H5`
- `Button 按钮`
- `item/tag`
- `Avatar 头像` when identity needs a person or merchant cue
