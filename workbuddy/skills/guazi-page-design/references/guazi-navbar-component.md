# Guazi NavBar Component

This reference is distilled from the `NavBar 导航栏` component page in the `Guazi Design` Figma library:

- file: `IlDoKwM2KnSOdvFyFskkP6`
- node: `24386:5240`

Use this reference whenever the page needs a title bar, top navigation area, or search-first header.

## 1. Component Families

The NavBar family includes three practical component groups:

- `NavBar 导航栏 - H5`
- `NavBar 导航栏 - mini program小程序`
- `SearchNavBar 搜索导航栏 - H5`

## 2. Default Routing

Choose in this order:

1. `NavBar 导航栏 - H5` for normal H5 page titles
2. `SearchNavBar 搜索导航栏 - H5` when search is the page's primary task
3. `NavBar 导航栏 - mini program小程序` only when mini-program behavior is explicitly required

Do not use the mini-program NavBar as the default page-title component for normal H5 pages.

## 3. `NavBar 导航栏 - H5`

Observed variant axes:

- `title`: `true`
- `type`: `middle | left`
- `right`: `default | 1icon | 2icon | text`
- `description`: `false | true`

Observed sizes:

- standard height is typically `48px`
- some description variants are `46px`
- width carrier is `375px` in Figma

Usage rules:

- Use this as the default page title bar for list pages, detail pages, and form pages
- Keep it fixed to the top for operational and transactional pages
- Keep the bar full width and visually aligned with the page shell
- Do not add visible shadow by default
- Prefer `type=middle` for standard standalone page titles
- Use `type=left` when the title is long, when the information hierarchy needs stronger left alignment, or when the page has more contextual header actions
- Use `right=default` when no explicit top-right action is required
- Use `right=1icon` or `right=2icon` only when the icon action is truly high-frequency
- Use `right=text` only when the top-right action is short and clearly secondary to the page title
- Use `description=true` only when the page really needs a secondary line near the title; do not introduce description text casually

## 4. `SearchNavBar 搜索导航栏 - H5`

Observed variant axes:

- `leftArrow`: `true | false`
- `type`: `search`
- `cancel`: `true | false`
- `searchButton`: `true | false`

Observed size:

- `375 x 48`

Usage rules:

- Use when searching is the page's primary action
- Prefer this over placing a normal title bar plus a separate search field when the page is search-first
- Use `cancel=true` only when the page behavior clearly includes an exit or temporary search mode
- Use `searchButton=true` when the flow expects an explicit submit action
- Use `searchButton=false` for instant-search or filter-as-you-type flows

## 5. `NavBar 导航栏 - mini program小程序`

Observed variant axes:

- `title`: `true | false`
- `leftArrow`: `true | false`
- `homeIcon`: `true | false`
- `size`: `default | large`
- `type`: `middle | left`
- `image`: `true | false`
- `search`: `true | false`

Observed sizes:

- default is typically `375 x 48`
- large title variant reaches `375 x 104`

Usage rules:

- Use only for mini-program pages or when the source design explicitly requires mini-program semantics
- `homeIcon=true` should remain a mini-program-specific affordance, not a generic H5 pattern
- `size=large` is a special large-header pattern; do not use it as the default page title bar
- `image=true` and `search=true` are specialized variants, not the normal choice for page titles

## 6. Page-Level Recommendations

### List page

- default: `NavBar 导航栏 - H5`
- search-first list: `SearchNavBar 搜索导航栏 - H5`
- title alignment: prefer `middle` unless the list title is long or the right-side action density is high

### Detail page

- default: `NavBar 导航栏 - H5`
- title alignment: `middle` for short titles, `left` for long record names or stronger information density
- description: use only when the detail page needs a compact secondary status line in the bar

### Form page

- default: `NavBar 导航栏 - H5`
- title alignment: prefer `middle`
- keep the top-right action light; the primary CTA belongs in the bottom action bar, not in the NavBar

## 7. Code And Figma Implications

- In code, treat the title bar as a fixed top shell and let the content scroll below it
- In Figma, use the real Guazi instance instead of rebuilding the title bar from primitives
- For componentized page output, keep the outer frame at `375px` and place the chosen NavBar instance at the top edge
