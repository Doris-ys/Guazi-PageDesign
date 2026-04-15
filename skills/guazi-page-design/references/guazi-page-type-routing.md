# Guazi Page Type Routing

Use this reference before any page implementation work. Its job is to turn product prose into a clear page type and matching rule stack.

## 1. Routing Order

Classify the page in this order:

1. Is the primary task to scan repeated records? -> `list page`
2. Is the primary task to read one object and act on that object? -> `detail page`
3. Is the primary task to enter, edit, upload, or submit information? -> `form page`
4. If the page mixes two or more of the above, choose the dominant type -> `hybrid page`

Do not choose `hybrid` by default. Only use it when two task types are both structurally important.

## 2. Quick Recognition Heuristics

### List page

Signals:

- repeated cards or rows
- search bar
- tabs or filters
- result count
- per-item action buttons

Typical user words:

- 列表
- 搜索
- 筛选
- tab
- 卡片
- 多条数据

### Detail page

Signals:

- one record, one object, or one order
- summary card plus multiple information sections
- progress, timeline, status, or evidence areas
- bottom sticky CTA

Typical user words:

- 详情
- 订单详情
- 记录详情
- 客户详情
- 线索详情
- 商机详情
- 状态流转
- 处理进度
- 待办事项
- 沟通记录

### Form page

Signals:

- required fields
- inputs, radios, switches, uploads, textarea
- validation
- save/submit buttons

Typical user words:

- 新建
- 编辑
- 申请
- 提交
- 上传材料
- 表单

### Hybrid page

Use when the page contains one dominant shell plus one large secondary module, for example:

- detail page with a large form section
- list page with a persistent creation drawer
- form page with an embedded searchable selector list

Rule:

- choose the dominant page type for the outer scaffold
- use the secondary pattern only inside the corresponding section

## 3. Output Required From Routing

Before implementation, produce these five decisions:

- page type
- dominant user goal
- primary CTA
- secondary CTA set
- required states

## 4. Rule Stack Per Page Type

### List page

Apply in this order:

1. `$guazi-design-style-guide`
2. `guazi-component-usage.md`
3. `guazi-list-page-layout.md`

### Detail page

Apply in this order:

1. `$guazi-design-style-guide`
2. `guazi-component-usage.md`
3. `guazi-detail-page-layout.md`

### Form page

Apply in this order:

1. `$guazi-design-style-guide`
2. `guazi-component-usage.md`
3. `guazi-form-page-layout.md`

### Hybrid page

Apply in this order:

1. `$guazi-design-style-guide`
2. `guazi-component-usage.md`
3. dominant page-pattern reference
4. secondary pattern only inside the relevant module

## 5. Common Misclassification Fixes

- If the user says "列表" but the page only shows one record with many sections, route to `detail page`.
- If the user says "详情" but the page is mostly repeated rows with search/filter, route to `list page`.
- If more than half of the page is editable fields or uploads, route to `form page` even when there is a summary card at the top.
- If the page has both detail and form sections, use the page's final goal to decide:
  - read and decide -> `detail page`
  - fill and submit -> `form page`
- If the page shows a single customer or merchant with tabs such as `待办事项 / 沟通记录` plus bottom follow-up actions, route to `detail page`, not `list page`.

## 6. Handoff Sentence Pattern

When helpful, state the routing decision explicitly:

- `This requirement is a form page with a detail summary header.`
- `This requirement is a list page; the search + filter scaffold is the dominant pattern.`
- `This requirement is a hybrid page, but the outer shell should follow the detail-page pattern.`
