# Guazi Toast Component

Use this reference when the page needs a lightweight transient feedback message, loading hint, success toast, warning toast, or failure toast.

This reference is distilled from the Figma library:

- file: `IlDoKwM2KnSOdvFyFskkP6`
- page node: `24386:5286`
- component set node: `26833:11004`
- file name: `Guazi Design`

## 1. Component Role

`Toast 轻提示` is the lightweight feedback layer for short-lived state communication.

Use it for:

- action result feedback
- loading feedback
- lightweight warnings
- brief failure reminders

Do not use it for:

- complex decisions
- confirm/cancel choice
- long-form explanation
- persistent page content

If the interaction needs a decision, route to `Dialog 对话框` instead.

## 2. Variant Axes

Observed directly from the component set:

- `direction`: `row | colum | -`
- `icon`: `true | false`
- `theme`: `- | success | error | warning | loading`
- `text`: `true | false`
- `errorCode`: `true | false`

Practical meaning:

- `row`: horizontal toast
- `colum`: vertical toast with icon above text
- `-`: special icon-only loading state

## 3. Observed Sizes

Common examples on the component page:

- only text row toast: `104 x 52`
- row icon + text toast: `118~132 x 52`
- multi-line text toast: `185 x 72`
- column icon + text toast: `104 x 108`
- icon-only loading toast: `80 x 80`
- error-code style toast: around `228 x 110`

Rule:

- keep Toast compact and content-bounded
- do not stretch it into banner or dialog proportions

## 4. Structural Patterns

The component page explicitly shows these patterns:

### Only Text 纯文字

Use for:

- neutral short confirmation
- short generic feedback

Rule:

- this is the lowest-noise default for simple non-semantic tips

### Multiple Rows Text 多行文字

Use for:

- slightly longer explanation
- narrow-space copy that needs wrapping

Rule:

- keep it short even when multiline; if the message becomes paragraph-like, it should not be a toast

### Horizontal Layout with Icon 带横向图标

Use for:

- common semantic success/error/warning/loading messages
- inline-like lightweight feedback

Default rule:

- this is the default semantic toast pattern

### Vertical Layout with Icon 带竖向图标

Use for:

- stronger feedback emphasis
- centered overlay-like lightweight feedback
- operation-complete or operation-failed hints that should be more noticeable

Rule:

- use when the feedback needs slightly more weight than a row toast, but still not a dialog

### Loading Status 加载状态

Use for:

- in-progress actions
- short waiting periods
- transient asynchronous feedback

Patterns:

- row + icon + text
- column + icon + text
- icon-only loading state

Rule:

- if the loading time is long or blocks the main flow heavily, pair with page-level loading or modal strategy instead of relying on toast alone

## 5. Theme Meaning

### `theme=-`

Use for:

- neutral text-only toast
- generic non-semantic hints

### `theme=success`

Use for:

- successful save
- completed operation
- positive result feedback

### `theme=error`

Use for:

- failed operation
- immediate error feedback

### `theme=warning`

Use for:

- cautionary reminder
- non-terminal risk notice

### `theme=loading`

Use for:

- request in progress
- short async waiting feedback

## 6. Error Code Pattern

The page also shows `errorCode=true` examples.

Use for:

- backend or system failure cases where a visible error code helps support or troubleshooting

Rule:

- use sparingly
- only expose error code when it is meaningful to support the workflow
- do not clutter ordinary user-facing success/warning toasts with codes

## 7. Selection Guidance

Choose the nearest toast pattern first:

- short neutral hint -> text-only row toast
- standard semantic result -> row toast with icon
- stronger center feedback -> column toast with icon
- in-progress state -> loading toast
- support-oriented failure -> error-code toast

## 8. Page-Level Usage Rules

### List page

Use for:

- quick success after item action
- quick failure after item action
- short loading feedback for lightweight operations

Rule:

- the toast should confirm the action result without interrupting scanning

### Detail page

Use for:

- copy success
- short save success
- lightweight operation result feedback

### Form page

Use for:

- save success
- submit success
- short validation-adjacent backend result

Rule:

- field-level validation should remain near the field; do not rely on toast alone for form correctness

## 9. Figma Output Rules

When building the componentized Figma frame:

- prefer the real `Toast 轻提示` instance for lightweight feedback
- choose row layout by default
- use column layout only when the feedback needs stronger centered emphasis
- keep toast styles distinct from `Dialog 对话框`; toast is transient and lighter-weight
