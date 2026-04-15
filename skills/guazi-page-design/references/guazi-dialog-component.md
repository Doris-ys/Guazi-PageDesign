# Guazi Dialog Component

Use this reference when the page needs a modal dialog, confirmation popup, feedback popup, input popup, or image-led popup.

This reference is distilled from the Figma library:

- file: `IlDoKwM2KnSOdvFyFskkP6`
- page node: `24386:5278`
- component set node: `27360:22241`
- footer component node: `27360:21896`
- file name: `Guazi Design`

## 1. Components In Scope

The Dialog page shows two closely related pieces:

1. `Dialog 对话框`
2. `item/footer`

Practical rule:

- use `Dialog 对话框` for the modal body shell
- use `item/footer` for the button area instead of rebuilding the footer manually

## 2. Dialog Variant Axes

Observed directly from the component set:

- `title`: `true | false`
- `content`: `true | false`
- `input`: `true | false`
- `image`: `- | top | middle`

Observed carrier width:

- standard dialog width: `311px`

Observed common heights:

- text-only dialog: around `134 / 150 / 182`
- input dialog: around `188 / 204 / 236`
- image dialog: around `308.9 / 328.9 / 352.9 / 360.9 / 384.9`

## 3. Footer Variant Axes

Observed directly from `item/footer`:

- `confirm-btn`: `true | false`
- `cancel-btn`: `true | false`
- `button-layout`: `horizontal | vertical | -`

Practical meaning:

- `horizontal` is the default two-button layout
- `vertical` is for stronger stacked emphasis or longer actions
- `-` appears when only one side of the footer is used

## 4. Dialog Types

The component page groups the dialog family into four types:

### Feedback Dialog 反馈类对话框

Use for:

- operation result feedback
- explanatory notices
- system guidance that needs acknowledgement

Typical pattern:

- title optional
- content often present
- one confirm button or a light cancel + confirm pair

Rule:

- use this when the main goal is informing, not choosing

### Confirmation Dialog 确认类对话框

Use for:

- secondary confirmation before a meaningful action
- risk acknowledgement
- destructive or irreversible action confirmation

Typical pattern:

- short title
- short explanatory content
- horizontal footer with cancel + confirm

Rule:

- this should be the default choice for confirm/cancel decision popups

### Dialog with Input 输入类对话框

Use for:

- quick inline collection of one short field
- pop-up edits that do not justify a full page
- reason input, code input, or short note confirmation

Typical pattern:

- title present
- input field in content area
- footer with confirm and optional cancel

Rule:

- use only for short structured input
- if the form has multiple fields or uploads, route to a full form page instead of a dialog

### Dialog with Image 带图片的对话框

Use for:

- visually-led feedback
- promotion-like explanation
- image-assisted confirmation or education

Image positions:

- `image=top`
- `image=middle`

Rule:

- use image dialogs only when the visual materially helps comprehension
- do not add decorative imagery to ordinary transactional confirmations

## 5. Style Rules

The page also separately documents these dialog styles:

- `Horizontal Base Button 水平基础按钮`
- `Vertical Base Button 垂直基础按钮`
- `Dialog with Close Button 带关闭按钮的对话框`

### Horizontal Base Button

Use for:

- standard confirm/cancel dialogs
- most transactional popups

Default rule:

- this is the default footer layout

### Vertical Base Button

Use for:

- when the primary and secondary actions need stronger visual separation
- when button labels are longer
- when the dialog is narrow in perception and stacked actions scan better

Rule:

- use sparingly; horizontal layout should still be the common case

### Dialog with Close Button

Use for:

- information-heavy dialogs
- image dialogs
- dismissible overlays where the user may want to close without reading action labels first

Rule:

- do not add a close button to every confirmation dialog by default
- prefer explicit footer actions as the main decision path

## 6. Content Rules

### Title

Use when:

- the dialog benefits from a clear topic line
- the action or feedback should be scannable immediately

Rule:

- keep titles short and explicit

### Content

Use when:

- the action needs explanation
- the user needs context before confirming

Rule:

- keep copy concise; dialogs are not mini pages

### Input

Use when:

- the user needs to type one short value or reason

Rule:

- avoid long-form multi-field forms in dialogs

### Image

Use when:

- the image clarifies the message
- the dialog is closer to a guided tip or visual feedback pattern

## 7. Page-Level Usage Rules

### List page

Use dialogs for:

- confirm destructive item actions
- quick reason input
- brief rule reminders

Rule:

- the dialog should support the list action, not replace the page flow

### Detail page

Use dialogs for:

- confirm state changes
- secondary evidence explanations
- quick edits that do not justify leaving the page

### Form page

Use dialogs for:

- submit confirmation
- abandonment warning
- short inline supplementary input

Rule:

- do not move the core form into a dialog unless the interaction is truly lightweight

## 8. Selection Guidance

Choose the nearest dialog pattern first:

- informative notice -> `Feedback Dialog`
- confirm / cancel decision -> `Confirmation Dialog`
- quick single-field edit -> `Dialog with Input`
- visually-led explanation -> `Dialog with Image`

Then choose footer style:

- ordinary two-action choice -> `horizontal`
- stronger stacked emphasis -> `vertical`
- dismissible info popup -> add close button only if needed

## 9. Figma Output Rules

When building the componentized Figma frame:

- prefer the real `Dialog 对话框` instance for popup shells
- prefer the real `item/footer` instance for button areas
- keep the dialog centered over a dimmed overlay instead of rebuilding ad hoc floating cards
- use the documented shadow/elevation style for overlays rather than page-card styling
