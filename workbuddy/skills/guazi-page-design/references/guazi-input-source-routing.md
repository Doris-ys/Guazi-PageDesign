# Guazi Input Source Routing

Use this reference before page-type routing. Its job is to identify what kind of input the user provided and choose the right extraction path.

## 1. Supported Input Sources

The skill should recognize these three primary inputs:

1. `需求文档`
2. `原型图`
3. `原型 HTML 文件`

The user may provide only one source or any combination of them.

## 2. Source Priority

When multiple sources are provided together, resolve conflicts in this order:

1. business rules and field logic -> `需求文档`
2. layout structure and module ordering -> `原型图` or `原型 HTML`
3. final visual language and component choice -> Guazi design rules and component library

Rule:

- never let a raw prototype override explicit business rules from the requirement document
- never let a raw HTML style override Guazi design-system rules

## 3. Recognition Heuristics

### `需求文档`

Typical signals:

- long-form prose
- headings such as `背景 / 需求详情 / 交互说明 / 接口 / 埋点`
- field tables, state descriptions, trigger conditions

Primary extraction task:

- identify page type
- split sections
- extract required fields and states
- extract CTA hierarchy
- infer loading / empty / error / permission states

Best use:

- business-complete page generation
- state and rule completeness
- interface and interaction planning

### `原型图`

Typical signals:

- Figma link
- screenshot
- image attachment
- low-fidelity or high-fidelity page sketch

Primary extraction task:

- identify visual sections
- identify spacing rhythm and density
- identify likely component mapping
- identify interaction affordance placement

Best use:

- layout restoration
- module hierarchy recovery
- component placement and card structure

### `原型 HTML 文件`

Typical signals:

- `.html` file
- pasted HTML markup
- static demo page
- exported prototype page

Primary extraction task:

- parse DOM structure
- identify repeated blocks, sections, buttons, and forms
- extract copy and information hierarchy
- separate structural intent from raw prototype styling

Best use:

- fast page reconstruction
- precise scaffold reuse
- conversion into production React + TypeScript + Tailwind code

## 4. Execution Path By Input Type

### A. Requirement document only

Use this path:

1. classify page type
2. extract modules, CTAs, and states
3. choose the nearest Guazi page scaffold
4. generate the page from business logic first

Output bias:

- stronger business completeness
- more complete state coverage
- layout based on Guazi standards when no visual source is given

### B. Prototype only

Use this path:

1. identify page shell and section hierarchy
2. map visual blocks to Guazi components
3. infer missing states and business placeholders
4. rebuild using Guazi rules instead of copying raw prototype style blindly

Output bias:

- stronger visual similarity
- more faithful module ordering
- business rules may need inference if not explicitly provided

### C. Prototype HTML only

Use this path:

1. parse structural blocks from the HTML
2. keep content hierarchy and interaction placement
3. replace raw styles with Guazi tokens and components
4. refactor into production page code

Output bias:

- fastest implementation path
- strongest structural fidelity
- must actively normalize away non-Guazi prototype styles

### D. Requirement + prototype

Use this path:

1. use the requirement as business truth
2. use the prototype for layout and module order
3. use Guazi rules for final component and visual decisions

This is the preferred combination.

### E. Requirement + HTML

Use this path:

1. use the requirement as business truth
2. use HTML for page scaffold and content grouping
3. replace prototype implementation with Guazi-compliant production code

### F. Requirement + prototype + HTML

Use this path:

1. requirement defines what the page must do
2. prototype and HTML define how the page is roughly organized
3. Guazi rules define how the final page should look and be componentized

This is the highest-confidence input combination.

## 5. Required Decisions Before Generation

Before coding, always state or internally resolve:

- input source type
- page type
- trusted source for business rules
- trusted source for layout
- trusted source for final visual rules
- missing information that must be inferred

## 6. Practical Normalization Rules

- Do not copy raw grayscale, shadow, radius, or spacing from a prototype if Guazi rules already define them.
- Do not preserve invalid or placeholder prototype copy when the requirement provides formal business wording.
- Do not preserve prototype-only controls that have no business meaning in the requirement unless the user explicitly wants them.
- When HTML or image prototypes are incomplete, generate the missing states from the requirement or from Guazi page-pattern rules.
