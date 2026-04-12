# Guazi Codex Skills

一套用于 Guazi 页面生成与 Figma 协同的 Codex skills 分享包。

## 包含内容

- `skills/guazi-page-delivery/`
  - 页面生成主技能
  - 支持三类输入：需求文档、原型图、原型 HTML
  - 自动识别页面类型，并按规范生成页面
- `skills/guazi-design-style-guide/`
  - 瓜子基础设计规范技能
  - 提供全局视觉规范、组件使用约束、页面布局规则

## 适用场景

- 根据需求文档生成列表页、详情页、表单页、个人中心页
- 根据 Figma 原型或 HTML 原型还原前端页面
- 按瓜子组件库规范生成代码
- 需要把页面方案同步回 Figma

## 安装方式

把本仓库中的两个技能目录复制到本机的 `~/.codex/skills/` 下：

```bash
mkdir -p ~/.codex/skills
cp -R skills/guazi-page-delivery ~/.codex/skills/
cp -R skills/guazi-design-style-guide ~/.codex/skills/
```

复制完成后，重新打开 Codex 或开启一个新会话。

## 使用方式

### 1. 直接调用页面生成技能

```text
使用 $guazi-page-delivery 根据需求文档生成一个订单详情页
```

### 2. 结合 Figma 链接生成页面

```text
使用 $guazi-page-delivery 根据这个 Figma 原型生成页面，并同步到 Figma
```

### 3. 结合 HTML 原型生成页面

```text
使用 $guazi-page-delivery 根据这个原型 HTML 生成页面
```

## 前置依赖

- 已安装并可用的 Codex
- 本机可读取 `~/.codex/skills/`
- 如果需要“同步到 Figma”：
  - 已安装 Figma MCP
  - 当前账号可访问对应的 Figma 文件和组件库

## 技能关系

- `guazi-design-style-guide`：定义“应该长什么样、组件怎么用、页面怎么排”
- `guazi-page-delivery`：定义“接到需求后怎么识别、怎么生成、怎么落到代码和 Figma”

可以理解为：

- 前者是规范底座
- 后者是交付流程

## 目录说明

```text
guazi-codex-skills/
├── README.md
├── GIT_UPLOAD_GUIDE.md
└── skills/
    ├── guazi-design-style-guide/
    └── guazi-page-delivery/
```
