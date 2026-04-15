# Guazi Form Page Layout

Use this reference for create, edit, apply, submit, or material-upload pages whose primary job is to collect user input.

## 1. Page Goal

A form page should help the user:

1. understand what must be filled
2. complete the required input efficiently
3. submit with confidence

## 2. Default Scaffold

The default form-page order is:

1. fixed top navbar
2. optional summary or identity card
3. grouped form-section cards
4. helper or policy text
5. sticky bottom action bar

## 3. Section Grouping

Group fields by task, not by raw schema.

Typical groups:

- base information
- operation choice
- explanation or remarks
- supporting materials

Rules:

- each card should solve one subtask
- do not mix uploads, freeform remarks, and structured fields in a random order

## 4. Field Order

Use this priority:

1. decision fields that change the form path
2. required structured fields
3. conditional fields
4. long-form explanation
5. uploads or evidence

## 5. Labels, Required State, And Helper Text

Rules:

- every field needs a visible label
- mark required fields consistently
- placeholders support the label; they do not replace the label
- use helper text for formats, examples, or review implications

## 6. Component Rules In Forms

- `Input 输入框` for short structured values
- prefer `layout=vertical`, `label=true`, `align=left` as the standard form-field baseline
- use horizontal input rows only for denser settings-like forms or tightly paired values
- `InputPassword 密码输入框` for concealed sensitive values
- `Radio` or horizontal radio for low-count mutually exclusive options
- `Switch 开关` only for direct toggles, not for review-heavy decisions
- `Textarea` for explanations
- `Upload` for supporting materials

## 7. Upload Areas

Rules:

- place uploads after the explanatory fields unless the upload determines the rest of the flow
- show required vs optional clearly
- provide sample guidance when the material has a quality expectation
- keep repeated upload rows visually consistent
- group uploads by material type instead of mixing all evidence into one area
- use single-file upload for one-per-field evidence and multi-file upload only for same-type repeated materials
- preserve failed / retry / loading states explicitly when the business flow depends on upload completion

## 7a. Helper Text And Validation

Rules:

- when a field has format requirements or review implications, prefer input variants with helper text rather than separate floating notes
- success / warning / error states should follow the Input family state language consistently
- do not rely on placeholder text alone to explain complex fields
- upload sections should also expose material guidance when file quality or type affects review

## 8. Action Bar

Use a sticky bottom action bar for important forms.

Rules:

- primary CTA: submit or confirm
- secondary CTA: save or cancel
- keep button order stable across forms
- do not mix many tertiary actions into the bottom bar

## 9. Common Form States

Form pages should consider:

- untouched default state
- partially filled state
- validation error state
- uploading state
- success or submitted state

## 10. Figma Reuse Guidance

Prefer:

- `NavBar 导航栏 - H5`
- `Input 输入框`
- `Button 按钮`
- `Switch 开关`
- `Upload`
- `Radio 单选`
