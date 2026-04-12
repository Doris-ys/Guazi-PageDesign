# Guazi Tabs Component

This reference is distilled from the `Tabs 选项卡` component page in the `Guazi Design` Figma library:

- file: `IlDoKwM2KnSOdvFyFskkP6`
- node: `24386:5243`

Use this reference whenever a page contains top-level category switching, content-section switching, or tabbed subviews.

## 1. Component Families

The Tabs family includes these practical groups:

- `Tabs 选项卡`
- `item/normal-line`
- `item/normal-noline`
- `item/tag`
- `item/tag-icon`
- `item/card`

## 2. Default Routing

Choose in this order:

1. `Tabs 选项卡` for the complete tab bar
2. let the component's `theme` decide the visual family rather than assembling tab items manually
3. use the item-level variants only when you are implementing code-level token mapping or inspecting states

Do not build a custom tab bar from independent chips or buttons if the Tabs family already fits the switching pattern.

## 3. `Tabs 选项卡`

Observed variant axes:

- `theme`: `normal | tag | card`
- `size`: `small | large`
- `item`: `2 | 3 | 4 | 5 | 6`
- `bottomline`: `on | off`
- `isometric`: `true | false`

Observed size:

- common carrier size is `375 x 48`

Usage rules:

- Use `theme=normal` as the default page-level switching pattern
- Use `theme=tag` for lighter, chip-like category switching when the tabs feel closer to filters than full section navigation
- Use `theme=card` only when the page visually needs stronger segmented panels
- Use `size=small` as the default dense H5 pattern
- Use `size=large` when the page needs stronger emphasis or more breathing room
- Set `item` to the actual tab count; do not fake equal-width tabs with the wrong count
- Use `bottomline=on` for classic top navigation tabs
- Use `bottomline=off` for tag or card-like switching patterns
- Use `isometric=true` when the tabs need equal-width distribution across the row
- Use `isometric=false` when the content or visual weight benefits from natural-width tab items

## 4. State Language

The component page explicitly demonstrates these tab-item states:

- selected
- default
- disabled
- badge on
- badge off

Usage rules:

- A selected tab should remain clearly stronger than default tabs
- Disabled tabs should remain visible but not interactive
- Badges should be used sparingly to indicate status count or attention cue, not to decorate every tab

## 5. Theme Guidance

### `theme=normal`

Use for:

- list page category switching
- top-level section switching
- stable page information architecture

Recommended defaults:

- `size=small`
- `bottomline=on`

### `theme=tag`

Use for:

- lightweight category switching
- compact secondary switching
- chip-like subfilters with clearer selected state than plain text

Recommended defaults:

- `bottomline=off`

### `theme=card`

Use for:

- panel-style switching
- stronger segmented selection where the selected area needs a more obvious container feel

Recommended defaults:

- `bottomline=off`

## 6. Page-Level Recommendations

### List page

- default: `theme=normal`
- prefer `size=small`
- prefer `bottomline=on`
- use `isometric=true` when the categories are peers and should share equal weight

### Detail page

- use tabs only when the detail content genuinely splits into clear peer sections
- prefer `theme=normal` or `theme=tag`
- avoid tabs when the page is better expressed as a vertical section stack

### Form page

- use tabs only when the form is truly multi-section and the sections are peer-level
- do not replace ordinary field grouping with tabs unless switching is necessary

## 7. Content-Area Pattern

The component page explicitly includes a `Tabs with Content` example.

Usage rules:

- When tabs control a content area, keep the tab bar directly attached to the corresponding content section
- Do not place unrelated cards or summary blocks between the tabs and the content they switch
- Keep the selected tab and the visible content section in clear visual pairing

## 8. Code And Figma Implications

- In code, map `theme`, `size`, `item`, `bottomline`, and `isometric` to props instead of creating page-specific tab implementations
- In Figma, use the real Guazi tabs instance rather than rebuilding tabs from buttons, tags, or text
- For componentized page output, keep the tab bar aligned to the `375px` frame width and match the page's switching hierarchy consistently
