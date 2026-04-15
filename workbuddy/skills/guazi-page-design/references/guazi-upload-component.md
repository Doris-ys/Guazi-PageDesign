# Guazi Upload Component

This reference is distilled from the `Upload 上传` component page in the `Guazi Design` Figma library:

- file: `IlDoKwM2KnSOdvFyFskkP6`
- node: `24386:5258`

Use this reference whenever a page contains image upload, evidence upload, re-upload, upload progress, upload failure, disabled upload, or single-vs-multiple material submission.

## 1. Component Families

The Upload family includes these practical groups:

- `Upload 上传`
- `item/file`

## 2. Default Routing

Choose in this order:

1. `Upload 上传` for all image-first or material upload areas
2. `item/file` only as the repeated tile inside the upload area, not as a standalone upload section

Do not invent a custom upload gallery if the Upload family already supports the material pattern.

## 3. `Upload 上传`

Observed variant axes:

- `multiple`: `true | false`
- `state`: `default | select`
- `fileItems`: `0 | 1 | 2 | 3 | 4 | 5 | 6`

Observed size patterns:

- single-line / one-row carrier: typically `375 x 150`
- wrapped multi-row carrier: typically `375 x 239`
- single-file card height still follows the same tile rhythm

Usage rules:

- Use `multiple=false` for single required image or single evidence upload
- Use `multiple=true` for galleries, multi-proof submission, or repeated materials of the same type
- Use `state=default` only for the truly empty initial state
- Use `state=select` once at least one file tile is present
- Let `fileItems` reflect the actual number of current files instead of hard-coding a visual example

## 4. `item/file`

Observed variant axes:

- `state`: `normal | done | loading | percent | reload | failed | disabled`
- `theme`: `picture | video`
- `content`: `true | false`

Observed tile size:

- typically `112 x 84`

Usage rules:

- Use `theme=picture` for ordinary image upload
- Use `theme=video` only when the submitted material is genuinely video-based
- Use `content=false` for the blank-slot or shell-style state
- Use `content=true` when a preview thumbnail is already available

## 5. Upload States

The component page explicitly demonstrates these states:

- normal
- done
- loading
- percent
- reload
- failed
- disabled

Usage rules:

- `loading` is for in-flight upload without a stable percent display
- `percent` is for uploads that expose progress numerically or visually
- `reload` is the retry pattern after a failed or interrupted upload
- `failed` should remain visually distinct from both loading and disabled
- `disabled` is for unavailable upload actions, not for completed uploads
- `done` is the normal uploaded-preview state

## 6. Style Patterns

The component page explicitly shows:

- single file upload
- multiple file upload
- wrapping mode
- single line mode

Usage rules:

- Use single-file upload for document fronts, backs, covers, or one-per-field evidence
- Use multiple-file upload for grouped materials such as gallery photos or repeated supporting evidence
- Use `wrapping mode` when the material count can exceed one visual row
- Use `single line mode` only when the uploaded item count is intentionally constrained and horizontal scan is preferred

## 7. Form-Page Recommendations

### Image-evidence forms

- default: `Upload 上传` with `theme=picture`
- use one upload group per material category
- keep required vs optional visible at the section or field label level

### Mixed material forms

- split upload groups by semantic type, such as 身份证、保单、截图、视频
- do not merge unrelated material types into one generic upload bucket

### Retry and review flows

- preserve failed and reload states instead of silently resetting the tile to empty
- when upload quality matters, keep retry affordance close to the failed tile

## 8. Code And Figma Implications

- In code, treat upload as a section-level component with repeated file tiles rather than a plain button
- Reuse a stable `112 x 84` tile rhythm for previews and the add slot
- In Figma, use the real Guazi upload instance for upload areas and file tiles whenever possible
- For componentized page output, keep upload groups aligned to the `375px` frame and maintain consistent single-line vs wrapping behavior
