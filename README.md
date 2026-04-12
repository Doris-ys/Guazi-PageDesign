# Guazi Page Design Skills

一套用于 Guazi 页面生成的技能包，主包面向 Codex，同时包含 WorkBuddy 兼容版，帮助团队把「需求描述 / 原型图 / 原型 HTML」稳定转成符合瓜子设计规范的页面方案，并支持继续同步到 Figma。

## 它能做什么

- 自动识别输入类型：需求文档、Figma 原型、原型 HTML
- 自动识别页面类型：列表页、详情页、表单页、个人中心页
- 按瓜子全局规范、组件规范、页面布局规范生成页面
- 在需要时支持把页面方案继续同步回 Figma
- 适合沉淀团队内部的页面交付流程和设计规范

## 适用场景

- 需求评审后，快速生成页面初稿
- 拿到 Figma 原型，生成符合组件库约束的前端页面
- 拿到 HTML 原型，规范化重建页面结构
- 把已有页面生成流程沉淀为团队可复用 skill

## 技能组成

### `guazi-design-style-guide`

基础设计规范层，负责回答这些问题：

- 页面整体视觉应该遵循什么规则
- 组件该怎么选、怎么用、什么场景下不要用
- 页面布局、间距、圆角、标题栏、卡片、标签等该怎么统一

### `guazi-page-delivery`

页面交付流程层，负责回答这些问题：

- 收到需求后先识别哪种输入来源
- 如何判断当前是列表页、详情页还是表单页
- 按什么顺序组织页面结构、组件和状态
- 什么时候需要同步回 Figma

可以把两者理解成：

- `guazi-design-style-guide` = 规范底座
- `guazi-page-delivery` = 交付工作流

## 仓库结构

```text
guazi-codex-skills/
├── CHANGELOG.md
├── GIT_UPLOAD_GUIDE.md
├── README.md
├── workbuddy/
└── skills/
    ├── guazi-design-style-guide/
    │   ├── SKILL.md
    │   ├── agents/
    │   └── references/
    └── guazi-page-delivery/
        ├── SKILL.md
        ├── agents/
        └── references/
```

## 快速安装

把仓库里的两个技能目录复制到本机的 `~/.codex/skills/` 下：

```bash
mkdir -p ~/.codex/skills
cp -R skills/guazi-page-delivery ~/.codex/skills/
cp -R skills/guazi-design-style-guide ~/.codex/skills/
```

复制完成后，重新打开 Codex 或开启一个新会话。

## WorkBuddy 版本

仓库里额外提供了一套 WorkBuddy 兼容版目录：

```text
workbuddy/
├── README.md
├── WORKBUDDY_INSTALL.md
└── skills/
```

如果你要给 WorkBuddy 使用，请看：

- `workbuddy/README.md`
- `workbuddy/WORKBUDDY_INSTALL.md`

## 使用示例

### 1. 根据需求文档生成页面

```text
使用 $guazi-page-delivery 根据需求文档生成一个订单详情页
```

### 2. 根据 Figma 原型生成页面

```text
使用 $guazi-page-delivery 根据这个 Figma 原型生成页面，并同步到 Figma
```

### 3. 根据 HTML 原型生成页面

```text
使用 $guazi-page-delivery 根据这个原型 HTML 生成页面
```

### 4. 只调用基础规范技能

```text
使用 $guazi-design-style-guide 输出这个页面应该遵循的设计规范
```

## 前置依赖

- 已安装并可用的 Codex
- 本机可读取 `~/.codex/skills/`
- 如果要同步到 Figma：
  - 已安装并可用的 Figma MCP
  - 当前账号有对应 Figma 文件和组件库的访问权限

## 推荐协作方式

如果你打算在团队内共享这套技能，建议这样维护：

- 规范更新时，优先更新 `guazi-design-style-guide`
- 页面生成流程变化时，更新 `guazi-page-delivery`
- 每次组件沉淀、页面类型补充、工作流调整后，更新 `CHANGELOG.md`
- 用 Git 仓库做统一分发，避免本地版本分叉

## 分享给同事时怎么说

你可以直接把下面这段发给对方：

```text
1. 克隆仓库
2. 把 skills/guazi-page-delivery 和 skills/guazi-design-style-guide 复制到 ~/.codex/skills/
3. 重启 Codex
4. 在会话里直接使用：使用 $guazi-page-delivery 根据需求文档生成页面
```

## 仓库地址

- GitHub: [Doris-ys/Guazi-PageDesign](https://github.com/Doris-ys/Guazi-PageDesign)

## 后续建议

这套仓库后面还可以继续补：

- 更多组件规范页
- 更多标准页面类型模板
- 更正式的版本号策略
- 示例输入与示例输出
- 团队协作约定和贡献指南
