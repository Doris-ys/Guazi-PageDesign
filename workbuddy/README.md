# WorkBuddy Skills Bundle

这一层目录提供的是 **WorkBuddy 兼容版** Guazi 技能包。

## 包含内容

- `skills/guazi-design-style-guide/`
- `skills/guazi-page-delivery/`

## 适合什么场景

- 你想在 WorkBuddy 中复用这套 Guazi 页面生成流程
- 你需要保留现有的 Guazi 规范文档和页面路由规则
- 你希望把 Codex 版技能迁移成更偏 WorkBuddy 的技能组织方式

## 安装位置

把 `skills/` 下的两个目录复制到：

```bash
~/.workbuddy/skills/
```

详细步骤见：

- `WORKBUDDY_INSTALL.md`

## 说明

- 这是一套 **兼容版迁移**，重点复用了规范、组件规则和页面交付流程
- 如果你的 WorkBuddy 环境没有 Figma 直连能力，技能会优先输出代码、页面方案或 Figma handoff 清单，而不是阻塞在同步步骤
