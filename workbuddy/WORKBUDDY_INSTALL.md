# WorkBuddy 安装说明

## 1. 复制技能目录

把这两个目录复制到本机的 `~/.workbuddy/skills/` 下：

```bash
mkdir -p ~/.workbuddy/skills
cp -R workbuddy/skills/guazi-design-style-guide ~/.workbuddy/skills/
cp -R workbuddy/skills/guazi-page-delivery ~/.workbuddy/skills/
```

## 2. 重新打开 WorkBuddy

复制完成后，建议重新打开 WorkBuddy，或者开启一个新会话。

## 3. 使用示例

```text
使用 $guazi-page-delivery 根据需求文档生成一个详情页
```

```text
使用 $guazi-page-delivery 根据这个原型 HTML 生成页面
```

```text
使用 $guazi-design-style-guide 输出这个页面应该遵循的瓜子规范
```

## 4. 兼容说明

这套 WorkBuddy 版本是从 Codex 版本迁移而来，重点保证以下能力可复用：

- 页面类型识别
- 输入来源识别
- 瓜子全局设计规范
- 组件使用规范
- 列表页 / 详情页 / 表单页布局规范

## 5. 关于 Figma

- 如果你的 WorkBuddy 环境支持 Figma 或相关设计工具集成，可以继续扩展“同步到 Figma”的流程
- 如果当前环境不支持，技能会优先输出：
  - 页面代码
  - 页面结构方案
  - Figma handoff 清单
