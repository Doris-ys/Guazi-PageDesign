# Guazi Input Component

This reference is distilled from the `Input 输入框` component page in the `Guazi Design` Figma library:

- file: `IlDoKwM2KnSOdvFyFskkP6`
- node: `24386:5249`

Use this reference whenever a page contains typed form entry, helper text, suffix actions, validation states, or special input patterns such as password, phone, code, quantity, or price.

## 1. Component Families

The Input family includes these practical groups:

- `Input 输入框`
- `InputPassword 密码输入框`
- `item/suffix`
- `item/label-horizontal`
- `item/label-vertical`

## 2. Default Routing

Choose in this order:

1. `Input 输入框` for standard text, number, ID, title, quantity, phone, and price input
2. `InputPassword 密码输入框` for hidden credential-style entry
3. `item/suffix` only as a sub-part of the input pattern, not as a standalone action row
4. `item/label-horizontal` or `item/label-vertical` when using the external-label pattern

Do not invent a custom input shell if the standard Input family already supports the field.

## 3. `Input 输入框`

Observed variant axes:

- `layout`: `horizontal | vertical | n/a`
- `label`: `true | false`
- `align`: `left | right`
- `suffix`: `true | false`
- `tips`: `true | false`
- `disable`: `true | false`
- `filled`: `true | false`

Observed size patterns:

- horizontal labeled input: typically `375 x 52`
- vertical labeled input: typically `375 x 80` or `375 x 84`
- with tips: typically `74 / 102` heights depending on layout
- no-label pattern: typically `52 / 74 / 80`
- grouped block/card examples use `56` row rhythm in the library examples

Usage rules:

- Use this as the default form input for standard typed fields
- Prefer `layout=vertical` for standard H5 forms and application pages
- Prefer `layout=horizontal` only for denser settings rows or compact data-entry groups
- Prefer `align=left` as the default readable pattern
- Use `align=right` only when the field behaves like a value row or key-value form line
- Keep `label=true` for most business forms; do not rely on placeholder-only labeling in reviewed flows
- Use `suffix=true` when the trailing control is part of the field semantics, such as picker entry, clear affordance, helper icon, inline button, or media cue
- Use `tips=true` when format guidance or review context is important
- Use `filled=true` only when the filled background pattern is already part of the page or state design
- Use `disable=true` for read-only or locked fields, not for fields that are merely optional

## 4. `InputPassword 密码输入框`

Observed variant axes:

- `layout`: `horizontal | vertical | n/a`
- `label`: `true | false`
- `align`: `left | right`
- `tips`: `true | false`
- `disable`: `true | false`
- `filled`: `true | false`

Usage rules:

- Use for passwords or concealed sensitive strings only
- Keep the password pattern separate from ordinary text inputs even if the visual shell is similar
- Follow the same layout choice as standard Input: vertical for most forms, horizontal only for dense rows

## 5. Special Input Patterns Shown In The Library

The component page explicitly shows these common use cases:

- labeled input
- required input
- optional input
- input with tips
- input with button
- input with selectable icon
- password input
- code input
- phone-number input
- price input
- quantity input

Practical rule:

- Prefer these built-in patterns before inventing new field compositions for common business forms

## 6. Input States

The component page explicitly demonstrates these states:

- active
- filled
- uneditable
- success
- warning
- error
- long label

Usage rules:

- Validation should use the built-in success / warning / error language instead of ad hoc color-only treatments
- Long labels are supported, but they should still be concise where possible
- If a field is uneditable, keep it visually distinct from merely empty fields

## 7. Style Patterns

The component page explicitly shows:

- horizontal layout
- vertical layout
- block style
- card style
- external label input

Usage rules:

- Use `vertical layout` as the default pattern for form pages
- Use `horizontal layout` for compact settings or side-by-side data entry
- Use `block style` for continuous stacked forms
- Use `card style` when fields are grouped inside white card containers
- Use `external label` only when the form needs stronger scanability or longer labels than the built-in field header comfortably supports

## 8. Suffix Guidance

The `item/suffix` set includes these observed trailing affordances:

- icon
- button
- text
- link
- image

Usage rules:

- Use suffix button or text only when it is semantically tied to the field, such as code retrieval or picker confirm
- Use suffix icon for helper, picker, clear, or status affordance
- Use suffix image only when the image is genuinely part of the input interaction
- Do not overload one field with multiple competing suffix actions

## 9. Page-Level Recommendations

### Form page

- default: `Input 输入框`
- preferred pattern: `layout=vertical`, `label=true`, `align=left`
- add `tips=true` for regulated, reviewed, or hard-to-understand fields
- add suffix only when the field needs a meaningful trailing action or cue

### Detail page with editable module

- use `Input 输入框` only inside the editable section
- prefer read-only display rows outside edit mode instead of exposing disabled inputs everywhere

### List page with search/filter

- use the search-specific header or compact field pattern rather than full vertical labeled inputs
- reserve full Input patterns for filter drawers or advanced filter modules

## 10. Code And Figma Implications

- In code, reuse the standard input shell and map the variant dimensions to props instead of rebuilding every field type
- In Figma, use real Guazi instances for form inputs and password inputs whenever possible
- For componentized page output, keep input fields aligned to the `375px` frame rhythm and match the chosen layout pattern consistently
