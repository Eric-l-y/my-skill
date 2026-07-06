# My Claude Skills

我的 Claude Code 个人技能库，包含日常开发中积累的经验和最佳实践。

---

## 安装（新电脑）

### 第一步：注册 marketplace

编辑 `~/.claude/plugins/known_marketplaces.json`，在顶层对象中添加：

```json
"my-skill": {
  "source": {
    "source": "github",
    "repo": "Eric-l-y/my-skill"
  },
  "installLocation": "C:\\Users\\你的用户名\\.claude\\plugins\\marketplaces\\my-skill",
  "lastUpdated": "2026-07-06T09:00:00.000Z"
}
```

> macOS/Linux 用户将路径改为 `/Users/你的用户名/.claude/plugins/marketplaces/my-skill`

### 第二步：安装插件

```bash
claude plugin install my-claude-skills@my-skill
```

---

## 更新

GitHub 仓库有新版本时，重新执行 install 命令即可自动更新：

```bash
claude plugin install my-claude-skills@my-skill
```

> 本地需要先手动同步 marketplace 目录（`~/.claude/plugins/marketplaces/my-skill/`），因为 Claude Code 不会自动从 GitHub 拉取自定义 marketplace 的更新。

---

## 使用

安装后技能会以 slash command 形式自动加载，在 Claude Code 中直接输入即可：

```
/code-review-checklist
/git-commit-style
/status
```

部分技能支持传参：

```
/code-review-checklist src/main.ts
/git-commit-style backend
```

---

## 技能列表

### 开发工作流

| 技能 | 说明 | 调用方式 |
|------|------|----------|
| `/code-review-checklist` | 代码审查检查清单，对当前 diff 进行系统化审查 | `/code-review-checklist [file]` |
| `/git-commit-style` | Git 提交信息规范，生成 Conventional Commits 格式的 commit message | `/git-commit-style [scope]` |
| `/status` | 快速查看当前项目状态（分支、变更、最近提交） | `/status` |

### 文档排版

| 技能 | 说明 |
|------|------|
| `/keyence-installation-manual` | 基恩士安装手册风格的 Word 排版规范（设备连接、系统配置、通讯设置等） |
| `/keyence-user-manual` | 基恩士用户手册风格的 Word 排版规范（产品使用说明书、操作手册、维护指南等） |
| `/yokogawa-spec-style` | 横河电机产品规格书风格的 Word 排版规范（工业产品技术文档、规格书等） |

---

## 许可

MIT
