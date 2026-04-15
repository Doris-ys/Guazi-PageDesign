# Guazi Search Component

This reference is distilled from the `Search 搜索框` component page in the `Guazi Design` Figma library:

- file: `IlDoKwM2KnSOdvFyFskkP6`
- node: `24386:5253`

Use this reference whenever a page contains keyword search, searchable filtering, or a compact search row above a list.

## 1. Component Family

The practical component group is:

- `Search 搜索框`

## 2. Default Routing

Choose in this order:

1. `Search 搜索框` for list-page keyword search
2. `SearchNavBar 搜索导航栏 - H5` when search is the page's dominant first-class shell action
3. ordinary `Input 输入框` only inside filter panels or advanced search forms, not for the main list search row

Do not replace the standard list-search component with a plain input field if the page is a classic searchable list.

## 3. `Search 搜索框`

Observed variant axes:

- `left-icon`: `true | false`
- `action`: `botton | icon`
- `fill`: `true | false`
- `style`: `grayBg | grayBorder | lightBorder | whiteBg`
- `dropDown`: `true | false`

Observed size:

- common carrier size is `375 x 52`

## 4. Variant Guidance

### `left-icon`

- Use `true` for classic search affordance with a leading search icon
- Use `false` only when the surrounding context already makes the search intent obvious

### `action`

- Use `botton` when the row needs an explicit trailing search action
- Use `icon` when the row needs a lighter trailing affordance

Practical rule:

- In most business list pages, explicit search action is clearer than icon-only submit

### `fill`

- Use `false` for default empty state
- Use `true` when the field contains input and the design should reflect a filled state

### `style`

- `grayBg`: best default for dense H5 operational lists
- `grayBorder`: use when the page needs slightly stronger field definition
- `lightBorder`: use sparingly for lighter bordered contexts
- `whiteBg`: use when the search row sits on a tinted or colored background and needs white contrast

Practical rule:

- Default to `grayBg` unless the page background or design system context makes another style clearly better

### `dropDown`

- Use `true` when the search row includes a category selector or scoped-search entry
- Use `false` for plain keyword search

## 5. State Language

The component page explicitly demonstrates:

- default state
- filled state

Usage rules:

- Keep the empty state lightweight and hint-like
- When the field contains text, keep the filled state readable and clearly editable
- Do not rely on placeholder text alone to communicate filter scope if the row also uses dropdown search scope

## 6. Page-Level Recommendations

### Operational list page

- default: `left-icon=true`, `action=botton`, `fill=false`, `style=grayBg`, `dropDown=false`
- place directly below tabs or navbar
- keep it full width on the `375px` frame

### Search-with-scope list page

- use `dropDown=true`
- keep the scope choice compact and clearly tied to the keyword field

### Search-first page

- prefer `SearchNavBar 搜索导航栏 - H5` instead of stacking a normal navbar plus `Search 搜索框`

## 7. Code And Figma Implications

- In code, treat the main list search row as its own component rather than reusing a generic input
- Map `left-icon`, `action`, `fill`, `style`, and `dropDown` to props if you implement the search row locally
- In Figma, use the real `Search 搜索框` instance for list search whenever possible
