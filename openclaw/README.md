# OpenClaw Skills Bundle

这一层目录提供的是 **OpenClaw 兼容版** Guazi 技能包。

## 包含内容

- `skills/guazi-design-style-guide/`
- `skills/guazi-page-design/`

## 适合什么场景

- 你想在 OpenClaw 中复用这套 Guazi 页面生成流程
- 你需要保留现有的 Guazi 规范文档和页面路由规则
- 你希望给 OpenClaw 用户提供单独可安装的技能目录

## 安装位置

把 `skills/` 下的两个目录复制到：

```bash
~/.openclaw/skills/
```

或者复制到当前工作区：

```bash
<workspace>/skills/
```

详细步骤见：

- `OPENCLAW_INSTALL.md`

## 说明

- 这是一套 **兼容版迁移**，重点复用了规范、组件规则和页面交付流程
- 按 OpenClaw 的技能 frontmatter 额外补充了 `metadata.openclaw`
- 如果你的 OpenClaw 环境没有 Figma 直连能力，技能会优先输出代码、页面方案或 Figma handoff 清单
