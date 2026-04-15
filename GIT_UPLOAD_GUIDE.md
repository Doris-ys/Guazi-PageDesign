# Git 上传指南

这份指南适合把当前分享包上传到一个新的 Git 仓库，例如 GitHub、GitLab 或 Gitee。

## 方案一：本地新建仓库再推送

先进入分享包目录：

```bash
cd /Users/xiaoyuzhou/Documents/Claw/skill-share/guazi-codex-skills
```

初始化 Git 仓库：

```bash
git init
git add .
git commit -m "chore: add guazi codex skills bundle"
```

然后去 Git 平台新建一个空仓库，比如：

- 仓库名：`guazi-codex-skills`

新仓库建好后，把远程地址替换成你的真实仓库地址：

```bash
git remote add origin <你的仓库地址>
git branch -M main
git push -u origin main
```

常见远程地址示例：

```bash
git remote add origin git@github.com:<your-name>/guazi-codex-skills.git
```

或者：

```bash
git remote add origin https://github.com/<your-name>/guazi-codex-skills.git
```

## 方案二：先在 GitHub/GitLab 下载桌面客户端再拖进去

如果你不想走命令行，也可以：

1. 在平台上创建空仓库
2. 用 GitHub Desktop / SourceTree 克隆到本地
3. 把当前目录下的文件拖进去
4. 提交并推送

## 推荐仓库内容

建议至少保留这些内容：

- `README.md`
- `GIT_UPLOAD_GUIDE.md`
- `skills/guazi-page-design/`
- `skills/guazi-design-style-guide/`

## 分享给别人时怎么说

你可以直接告诉对方：

1. 拉取仓库
2. 把 `skills/` 里的两个目录复制到 `~/.codex/skills/`
3. 重启 Codex
4. 在会话里直接使用：

```text
使用 $guazi-page-design 根据需求文档生成页面
```

## 更新技能时的维护方式

后续你如果继续沉淀组件或页面规范，建议按下面方式更新：

```bash
cd /Users/xiaoyuzhou/Documents/Claw/skill-share/guazi-codex-skills
git add .
git commit -m "docs: update guazi page delivery rules"
git push
```
