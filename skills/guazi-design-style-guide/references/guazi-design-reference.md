# Guazi Design Reference

This reference is distilled from the Figma library `Guazi Design` (`IlDoKwM2KnSOdvFyFskkP6`) using Figma MCP metadata and design-system search.

## 1. System Character

- The documentation pages explicitly reference TDesign concepts and token taxonomy.
- Inference: Guazi Design is a Guazi-branded adaptation of a TDesign-style system rather than a completely custom token model.
- Practical rule: keep TDesign-like token semantics, but use Guazi's published visual values.

## 2. Core Color Rules

### Brand / Success Green

These values are explicitly shown in the `Color_Light Mode` page:

- `Brand1 / Success / Light`: `#EBF9F5`
- `Brand1 / Success / Focus`: `#CCEFE4`
- `Brand1 / Success / Disabled`: `#9BE0CB`
- `Brand1 / Success / Normal`: `#00AE78`
- `Brand1 / Success / Click`: `#00875D`

Use this ramp for:

- Primary buttons
- Selected tabs and active indicators
- Success status chips
- Positive switches and confirmations

### Error

- `Light`: `#FFF1ED`
- `Focus`: `#FFDBD1`
- `Disabled`: `#FFB8A3`
- `Normal`: `#D54941`
- `Click`: `#BF3A3A`

### Warning

- `Light`: `#FFF1E9`
- `Focus`: `#FFECCC`
- `Disabled`: `#FFDA99`
- `Normal`: `#E37318`
- `Click`: `#BE5A00`

### Text and Icon Colors

The `文字&图标色` page exposes these neutral text ramps:

- `Font Gy1`: `#1E2225` for primary text
- `Font Gy2`: `#5F6670` for secondary text
- `Font Gy3`: `#8F96A0` for tertiary / hint text
- `Font Gy4`: `#BAC2C9` for disabled text

White-on-color alpha tokens:

- `Font Wh1`: `#FFFFFF` at `100%`
- `Font Wh2`: `#FFFFFF` at `55%`
- `Font Wh3`: `#FFFFFF` at `35%`
- `Font Wh4`: `#FFFFFF` at `22%`

### Color Usage Guidance

- Default page background can be a very light neutral or brand-tinted light background, but cards stay white.
- Use Guazi green as the single main accent unless the UI is semantically warning or destructive.
- Do not mix the Guazi green with unrelated blue or purple accents.

## 3. Radius Rules

The `Radius` page explicitly documents:

- `@radius-small: 2px` for very small elements such as compact badges
- `@radius-default: 4px` for controls like buttons, inputs, and tags
- `@radius-large: 8px` for cards
- `@radius-extraLarge: 12px` for panels, dialogs, popovers
- `@radius-round: 999px` for pill controls
- `@radius-circle: 50%` for circular avatars and icon buttons

Preferred usage:

- Inputs / buttons / tags: `4px`
- Card items: `8px`
- Large panels: `12px`
- Pills / capsules: `999px`
- Avatars: `50%`

Do not jump to `16px`, `20px`, or `24px` corners unless the source design explicitly overrides the library.

## 4. Shadow Rules

The `Shadow` page documents three elevation tokens:

- `@td-shadow-1`
  - `0 1px 10px rgba(0, 0, 0, 5%), 0 4px 5px rgba(0, 0, 0, 8%), 0 2px 4px -1px rgba(0, 0, 0, 12%)`
  - Use for hoverable surfaces such as tables or drag states
- `@td-shadow-2`
  - `0 3px 14px 2px rgba(0, 0, 0, 5%), 0 8px 10px 1px rgba(0, 0, 0, 6%), 0 5px 5px -3px rgba(0, 0, 0, 10%)`
  - Use for dropdowns, popovers, and selectors
- `@td-shadow-3`
  - `0 6px 30px 5px rgba(0, 0, 0, 5%), 0 16px 24px 2px rgba(0, 0, 0, 4%), 0 8px 10px -5px rgba(0, 0, 0, 8%)`
  - Use for notifications and high-elevation overlays

Rule of thumb:

- Most normal page cards should be flat and border-separated.
- Use no visible shadow for headers and cards by default.
- Only use the documented shadows for floating layers such as dropdowns, popovers, and overlays.
- Avoid exaggerated blur or colorful shadows.

## 5. Typography Rules

From the typography pages:

- Preferred Chinese font on macOS: `PingFang SC`
- Dominant weights: `Regular` and `Semibold`
- Explicit rule from the docs: `line-height = font size + 8`

Observed token examples in the typography section:

- `@font-size-displayLarge: 64px`
- `@font-size-displayMedium: 48px`
- `@font-size-markLarge: 16px`
- `@font-size-markMedium: 14px`
- `@font-size-markSmall: 12px`
- `@font-size-markExtraSmall: 10px`
- `@font-size-bodySmall: 12px`
- `@font-size-bodyExtraSmall: 10px`
- `@font-size-linkSmall: 12px`

Implementation guidance:

- Use semibold for page titles, section titles, emphasized labels
- Use regular for body copy, helper copy, descriptions
- For product/mobile interfaces, common body sizes will usually be `10 / 12 / 14 / 16`
- Derive line-height with the library rule instead of ad hoc compressed line-height values

## 6. Published Component Map

The following published components were discoverable through Figma MCP search:

- `Button 按钮`
- `NavBar 导航栏 - mini program小程序`
- `NavBar 导航栏 - H5`
- `Tabs 选项卡`
- `Input 输入框`
- `InputPassword 密码输入框`
- `Switch 开关`
- `Avatar 头像`
- `AvatarGroup 头像组`
- `CheckTag 可选标签`
- `item/tag`
- `item/card`
- `item/normal-line`
- `item/normal-line&icon`
- `item/normal-noline`
- `item/normal-noline&icon`
- `item/card-icon`

## 7. High-Value Component Variants

These were inspected directly from the published sets:

### `Button 按钮`

Observed component axes:

- `variant`: `base | outline | text | ghost`
- `theme`: `primary | light | default | text`
- `size`: `large | medium | small | extraSmall`
- `shape`: `rectangle | square`
- `prefixIcon`: `true | false`
- `suffixIcon`: `true | false`
- `singleIcon`: `true | false`
- `press`: `true | false`
- `disabled`: `true | false`

Observed practical rules:

- control radius: `4px`
- `large`:
  - height: `44px`
  - text: `16 / 22`, semibold
  - icon: `22px`
- `medium`:
  - height: `40px`
  - text: `14 / 20`, semibold
  - icon: `20px`
- `small`:
  - height: `32px`
  - text: `14 / 20`, semibold
  - icon: `18px`
- `extraSmall`:
  - height: `28px`
  - text: `12 / 18`, semibold
  - icon: `16px`

Usage guidance:

- use `large` for form submit and page-primary CTA
- use `medium` for ordinary page and popup actions
- use `small` for compact toolbars
- use `extraSmall` for dense list-card actions
- use square shape for icon-only buttons
- keep the primary action on the far right in horizontal button groups

### `NavBar 导航栏 - mini program小程序`

Variant axes:

- `title`: `true | false`
- `leftArrow`: `false | true`
- `homeIcon`: `false | true`
- `size`: `default | large`
- `type`: `middle | left`
- `image`: `false | true`
- `search`: `false | true`

Text property:

- title text property exists

Usage:

- For standard web detail pages, prefer `NavBar 导航栏 - H5`
- For standard mobile profile/detail pages, use `NavBar 导航栏 - mini program小程序` only when mini-program behavior is explicitly required
- In transactional H5 pages, keep the header fixed at the top and aligned to the same content width as the page shell
- `size=large` is a specialized large-header pattern, not the default page title bar
- `homeIcon=true` remains a mini-program-specific affordance

### `NavBar 导航栏 - H5`

Variant axes observed from the component page:

- `title`: `true`
- `type`: `middle | left`
- `right`: `default | 1icon | 2icon | text`
- `description`: `false | true`

Observed dimensions:

- default width carrier: `375px`
- standard height: `48px`
- some description variants: `46px`

Usage:

- Treat this as the default page-title component for H5 list, detail, and form pages
- Prefer `type=middle` for standard standalone page titles
- Use `type=left` for longer titles or denser contextual headers
- Use `right=1icon` or `right=2icon` only when the top-right icon action is truly high-frequency
- Keep the H5 navbar fixed to the top and full width in transactional pages
- Avoid visible shadow by default

### `SearchNavBar 搜索导航栏 - H5`

Variant axes observed from the component page:

- `leftArrow`: `true | false`
- `type`: `search`
- `cancel`: `true | false`
- `searchButton`: `true | false`

Observed dimensions:

- standard size: `375 x 48`

Usage:

- Use this when search is the dominant page action
- Prefer it over stacking a normal title bar plus a duplicated search row in search-first pages
- Use `cancel=true` for temporary or modal-like search flows
- Use `searchButton=false` for instant-search behavior

### `Tabs 选项卡`

Variant axes:

- `theme`: `normal | tag | card`
- `size`: `small | large`
- `item`: `2 | 3 | 4 | 5 | 6`
- `bottomline`: `off | on`
- `isometric`: `false | true`

Usage:

- For content tabs in standard pages, prefer `theme=normal`
- Use `item=3` when building the common `动态 / 收藏 / 设置` pattern
- Prefer `size=small` for dense H5 pages
- Prefer `bottomline=on` for classic page-level top switching
- Use `isometric=true` when the categories should share equal visual weight across the row
- Use `theme=tag` for chip-like secondary switching and `theme=card` for stronger segmented switching

### `Input 输入框`

Variant axes:

- `layout`: `horizontal | vertical | n/a`
- `label`: `true | false`
- `align`: `left | right | center`
- `suffix`: `false | true`
- `tips`: `false | true`
- `disable`: `false | true`
- `filled`: `false | true`

Usage:

- Use vertical layout for mobile settings forms
- Keep labels visible for settings and account forms
- Prefer filled or lightly tinted containers over sharp, dark bordered fields
- `align=left` is the default readable pattern; `align=right` is better reserved for denser value-row patterns
- The component page explicitly includes built-in patterns for required, optional, tips, button, selectable icon, phone, code, price, and quantity inputs
- The component page also demonstrates status patterns: active, filled, uneditable, success, warning, error, and long label

### `InputPassword 密码输入框`

Variant axes observed from the component page:

- `layout`: `horizontal | vertical | n/a`
- `label`: `true | false`
- `align`: `left | right`
- `tips`: `false | true`
- `disable`: `false | true`
- `filled`: `false | true`

Usage:

- Use for concealed sensitive values only
- Keep it aligned with the standard Input layout choice rather than creating a special page-specific password shell

### `Tag 标签`

Variant axes observed from the component page:

- `variant`: `dark | light | outline | lightOutline`
- `theme`: `default | primary | warning | danger | success | Sales`
- `size`: `large | medium | small`
- `shape`: `square`
- `prefixIcon`: `false | true`
- `closable`: `false | true`
- the page also explicitly documents disabled examples; treat disabled as a supported state

Observed dimensions:

- `large`: `20px` height
- `medium`: `18px` height
- `small`: `16px` height

Usage:

- Use this as the primary tag family for new Guazi status and metadata chips
- Prefer `theme=default` for neutral metadata and `variant=light` or `lightOutline` on white cards
- Use `theme=warning | danger | success` only for real semantic states
- Prefer `size=small` for dense list metadata and `size=medium` near detail titles
- Use `prefixIcon=true` only when the icon adds semantic value
- Use `closable=true` only for removable tags, not for read-only status

### `CheckTag 可选标签`

Usage:

- Use this for selectable chip controls, checked filters, and toggled tag selections
- Do not substitute ordinary read-only status tags with `CheckTag`

### `Dialog 对话框`

Variant axes observed from the component page:

- `title`: `true | false`
- `content`: `true | false`
- `input`: `true | false`
- `image`: `- | top | middle`

Observed dimensions:

- standard width: `311px`
- text-only heights commonly around `134 / 150 / 182`
- input variants commonly around `188 / 204 / 236`
- image variants commonly around `308.9 / 328.9 / 352.9 / 360.9 / 384.9`

Related footer component:

- `item/footer`
- `confirm-btn`: `true | false`
- `cancel-btn`: `true | false`
- `button-layout`: `horizontal | vertical | -`

Usage:

- Use this as the default modal shell for confirmation, feedback, input, and image-led popups
- Prefer horizontal footer actions for ordinary confirm/cancel decisions
- Use vertical footer actions only when the hierarchy or label length truly benefits
- Use close-button variants mainly for information-heavy or image-led dialogs
- Keep dialogs centered over an overlay and do not style them like ordinary page cards

### `Toast 轻提示`

Variant axes observed from the component page:

- `direction`: `row | colum | -`
- `icon`: `true | false`
- `theme`: `- | success | error | warning | loading`
- `text`: `true | false`
- `errorCode`: `true | false`

Observed dimensions:

- text-only row toast: about `104 x 52`
- row icon + text toast: about `118~132 x 52`
- multiline text toast: about `185 x 72`
- column icon + text toast: about `104 x 108`
- icon-only loading toast: about `80 x 80`

Usage:

- Use this as the default lightweight feedback component
- Prefer row layout for ordinary semantic feedback
- Use column layout for slightly stronger centered feedback
- Use loading theme only for short in-progress hints
- Keep toast copy short and transient; if the user must decide or read deeply, use `Dialog 对话框` instead

### `Search 搜索框`

Variant axes observed from the component page:

- `left-icon`: `true | false`
- `action`: `botton | icon`
- `fill`: `true | false`
- `style`: `grayBg | grayBorder | lightBorder | whiteBg`
- `dropDown`: `true | false`

Observed dimensions:

- standard size: `375 x 52`

Usage:

- Use this as the default keyword-search component for searchable list pages
- Prefer `grayBg` as the default dense H5 list-search style
- Prefer a leading search icon plus explicit trailing search action for operational lists
- Use `dropDown=true` only when scoped search is genuinely needed

### Input supporting subcomponents

Observed from the component page:

- `item/suffix`: supports `icon | button | text | link | image`
- `item/label-horizontal`: supports `required=true | false`
- `item/label-vertical`: supports `required=true | false`

Usage:

- Use suffix affordances only when they are semantically part of the field
- Use external labels when the label needs stronger prominence or longer copy than the built-in field header comfortably allows

### `Upload 上传`

Variant axes observed from the component page:

- `multiple`: `true | false`
- `state`: `default | select`
- `fileItems`: `0 | 1 | 2 | 3 | 4 | 5 | 6`

Observed dimensions:

- common carrier sizes: `375 x 150` and `375 x 239`

Usage:

- Use `multiple=false` for single evidence uploads
- Use `multiple=true` for repeated materials of the same category
- Use wrapped layout when the uploaded item count can exceed one row
- Preserve loading, retry, failed, and disabled states explicitly in business forms

### `item/file`

Variant axes observed from the component page:

- `state`: `normal | done | loading | percent | reload | failed | disabled`
- `theme`: `picture | video`
- `content`: `true | false`

Observed dimensions:

- standard tile size: `112 x 84`

Usage:

- Use `theme=picture` for image upload and `theme=video` for video material
- Use `done` as the normal preview state after upload
- Use `reload` and `failed` instead of collapsing back to an empty tile when retry is part of the flow

### `Switch 开关`

Variant axes:

- `sized`: `large | medium | small`
- `label`: `none | icon | text`
- `disabled`: `false | true`
- `value`: `true | false`
- `loading`: `false | true`

Usage:

- Prefer `medium` for settings rows
- Keep label inside the row, not inside the switch itself, unless the source design asks for it

### `Avatar 头像`

Variant axes:

- `size`: `small | medium | large`
- `shape`: `circle | round`
- `image`: `false | true`
- `icon`: `false | true`

Usage:

- Prefer `circle`
- Use image mode for real profile UIs when an image exists
- Use text fallback or icon fallback only when no photo source is available

## 8. Composition Rules

When an exact component is missing:

- Compose from `Avatar 头像`, `item/card`, `item/tag`, text tokens, and documented radii
- Keep white surfaces, restrained shadows, and Guazi green as the dominant accent
- Preserve a compact mobile rhythm; this library does not suggest oversized hero cards or luxury-dashboard spacing

Good fallback examples:

- `AvatarCard` = `Avatar 头像` + white 8px card + `Font Gy1/Gy2` text
- profile stats row = `item/tag` or `CheckTag 可选标签` when appropriate

## 9. Figma-to-Code Guidance

- Search published components by their exact bilingual names before hand-building a replacement
- Mirror the library naming in your component wrappers when possible to keep design/code mapping legible
- If coding in React + Tailwind, encode the Guazi tokens in local utility choices instead of approximate defaults
- Avoid default Tailwind gray/emerald choices when they diverge from the documented Guazi values; prefer exact hex values or mapped project tokens

## 10. Recommended Defaults for Mobile Screens

Use these defaults unless the target design says otherwise:

- for responsive H5 pages: `width: 100%` with a centered content container
- for mini-program/mobile mocks: `375`
- primary accent: `#00AE78`
- primary text: `#1E2225`
- secondary text: `#5F6670`
- input/button/tag radius: `4px`
- card radius: `8px`
- panel radius: `12px`
- line-height: `font-size + 8`

These defaults are conservative and align with the observed Guazi library guidance.

## 11. Responsive H5 Overrides

When building H5 transactional pages such as order detail, service detail, or payout detail:

- Prefer `NavBar 导航栏 - H5`
- Fix the header to the top of the viewport
- Keep the header and page container visually equal in width
- Use border and background separation instead of elevation for both header and cards
- Let the main content expand and contract with the screen width; do not lock the whole page to a `375px` shell
- On larger screens, allow content sections to reflow into columns only when readability improves
- Default page outer padding: `10px`
- Default card-to-card gap: `10px`
- Default card inner padding: `14px`
- Cards should not have gray borders by default; rely on white surfaces plus spacing unless the source design explicitly asks for outlined cards
