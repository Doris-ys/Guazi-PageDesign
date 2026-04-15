# Changelog

本文档用于记录 `Guazi Page Design Skills` 仓库的重要更新。

## 2026-04-15

### Skills sync and compatibility alignment

- 修复各 `SKILL.md` frontmatter 中 `description` 的冒号解析风险：
  - 统一改为带引号的 YAML 字符串，避免 `:` 在描述文本中触发解析歧义
- 主版本 `guazi-page-design` 已同步最新规则到分享仓库：
  - 遇到原型图先分析结构（页面骨架、模块顺序、卡片层级、操作层级）
  - 再按 Guazi 设计规范生成页面，不直接照抄原型视觉
- WorkBuddy 兼容版同步主版本关键改动：
  - 增加原型图结构优先规则
  - 增加“原型图只作为结构来源，样式与组件选择遵循 Guazi 规范”规则
- OpenClaw 兼容版同步主版本关键改动：
  - 增加原型图结构优先规则
  - 增加“原型图只作为结构来源，样式与组件选择遵循 Guazi 规范”规则

## 2026-04-12

### Initial release

- 初始化分享仓库 `guazi-codex-skills`
- 收录 `guazi-design-style-guide` 基础设计规范技能
- 收录 `guazi-page-design` 页面交付流程技能
- 补充页面生成输入路由规则：
  - 需求文档
  - Figma 原型
  - 原型 HTML
- 补充页面类型路由规则：
  - 列表页
  - 详情页
  - 表单页
  - 个人中心页
- 沉淀并收录以下组件规范：
  - Navbar
  - Input
  - Upload
  - Tabs
  - Search
  - Tag
  - Dialog
  - Toast
- 补充标准页面规范：
  - 列表页布局规范
  - 详情页布局规范
  - 表单页布局规范
- 补充分享仓库说明文档与 Git 上传说明
- 新增 WorkBuddy 兼容版技能目录与安装说明
- 新增 OpenClaw 兼容版技能目录与安装说明
