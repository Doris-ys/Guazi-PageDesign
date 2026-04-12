# Guazi Standard List Examples

This reference is distilled from the Figma file:

- file: `G38oVi0JYCVmv4G6GWkSSo`
- page node: `2:3`
- file name: `车优多-零售`

The file contains three standard list-like samples. Use them as concrete examples when implementing Guazi list pages.

## 1. Sample Set Overview

Observed sample pages:

1. `收款信息`
2. `订单列表 - 零售订单` variant A
3. `订单列表 - 零售订单` variant B

Practical classification:

- `收款信息` is a list-style detail page with repeated account cards and a sticky bottom summary
- the two `订单列表` screens are standard operational list pages with tabs, search, quick filters, and repeated order cards

## 2. Shared List-Shell Pattern

Across the operational list pages, the common scaffold is:

1. status bar
2. `NavBar 导航栏 - H5`
3. `Tabs 选项卡`
4. search bar
5. quick filter chip row
6. repeated white cards
7. home indicator / bottom safe area

Rule:

- For operational order-like lists, treat this as the default first-screen structure before inventing custom scaffolds

## 3. Order List Pattern

Use when the page is primarily for scanning repeated vehicle/order records and taking per-item next-step actions.

### Header zone

- H5 navbar at top
- tabs directly below navbar
- search field directly below tabs
- compact quick filters below search

### Quick filters

Observed pattern:

- 4 compact buttons in one row
- compact height around `28px`
- used for business status shortcuts such as `交车中12` or `交易失败`

Rule:

- Use compact quick filters only when they materially reduce scan cost
- Keep the count small and horizontally scannable

### Card structure

Observed card pattern:

1. top line: order number / record ID on the left, business status on the right
2. middle: vehicle thumbnail on the left, title + vehicle meta on the right
3. tag row under title/meta
4. optional process reminder or gray helper strip
5. bottom action row with 1 to 3 compact actions

Rule:

- Keep vehicle/record identity concentrated near the thumbnail
- Keep business status in the top-right of the card head
- Keep process warnings in a low-elevation helper strip rather than mixing them into the core title block

### Action row

Observed pattern:

- compact action chips or buttons
- actions aligned to the right half of the footer
- count stays small

Rule:

- Prefer compact secondary actions plus one clearer primary business action
- Do not overload the card with long button text

## 4. Account Card List Pattern

Use when the page contains repeated account or payment information blocks with a strong summary amount at the bottom.

### Page structure

Observed pattern:

1. navbar
2. product/record summary strip with image and title
3. section title
4. repeated white information cards
5. sticky bottom summary bar

### Card structure

Observed card pattern:

1. left accent bar + section title
2. repeated key-value rows
3. emphasized amount row in orange/red

Rule:

- Use this pattern for finance/account/info-card lists rather than the operational order-card pattern
- Repeated finance cards can be taller and more row-based than order cards

### Bottom summary

Observed pattern:

- sticky bottom bar
- left label for total
- right strong amount

Rule:

- Use a sticky summary bar only when the page has a cumulative value that must remain visible during scan

## 5. Variant A vs Variant B In Order Lists

The two `订单列表` examples show the same outer scaffold with different card density.

### Variant A

- simpler card
- lighter footer
- fewer helper strips

Best for:

- cleaner operational lists
- earlier-stage order states
- lower action density

### Variant B

- denser card
- includes helper strip and more action controls
- stronger process-oriented footer

Best for:

- negotiation / fulfillment / multi-step progress states
- pages where each card needs follow-up handling

## 6. Selection Guidance

When implementing a new Guazi list page, choose the nearest example first:

- If it is a vehicle/order operational list -> start from the `订单列表` pattern
- If it is a repeated account or finance info list -> start from the `收款信息` pattern
- If the cards need heavy process actions -> lean toward `订单列表` variant B
- If the cards are mostly for scan + one next step -> lean toward `订单列表` variant A
