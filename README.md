# My Claude Skills

我的 Claude Code 个人技能库，包含工业文档排版规范和日常开发最佳实践。

每个技能都是独立的 marketplace plugin，可单独安装。

---

## 安装

### 方式一：从 GitHub 安装（推荐）

#### 1. 注册 marketplace

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

#### 2. 安装需要的技能

每个技能是独立 plugin，按需安装：

```bash
# 工业文档排版
claude plugin install keyence-user-manual@my-skill
claude plugin install keyence-installation-manual@my-skill
claude plugin install yokogawa-spec-style@my-skill

# 开发工作流
claude plugin install code-review-checklist@my-skill
claude plugin install git-commit-style@my-skill
```

### 方式二：本地开发

在仓库根目录执行：

```bash
claude plugin install --local ./plugins/keyence-user-manual
```

---

## 更新

GitHub 仓库有新版本时，重新执行 install 命令即可自动更新：

```bash
claude plugin install keyence-user-manual@my-skill
```

> 本地需要先手动同步 marketplace 目录（`~/.claude/plugins/marketplaces/my-skill/`），因为 Claude Code 不会自动从 GitHub 拉取自定义 marketplace 的更新。

---

## 技能列表

### 工业文档排版

| 技能 | 说明 | 适用场景 |
|------|------|----------|
| `keyence-user-manual` | 基恩士用户手册风格的 Word 排版规范 | 产品使用说明书、操作手册、维护指南 |
| `keyence-installation-manual` | 基恩士安装手册风格的 Word 排版规范 | 设备连接指南、系统配置、通讯设置 |
| `yokogawa-spec-style` | 横河电机产品规格书风格的 Word 排版规范 | 工业产品技术文档、规格书、产品手册 |

### 开发工作流

| 技能 | 说明 |
|------|------|
| `code-review-checklist` | 代码审查检查清单，对当前 diff 进行系统化审查 |
| `git-commit-style` | Git 提交信息规范，生成 Conventional Commits 格式的 commit message |

---

## 使用

安装后技能会自动加载，在 Claude Code 中按需触发：

- 技术文档排版：发送请求时描述目标文档类型即可
- 代码审查：使用 `review` / `审查` 触发
- 提交信息：使用 `commit` / `提交` 触发

---

## 项目结构

```
my-skill/
├── .claude-plugin/
│   └── marketplace.json        # marketplace 配置，列出所有 plugins
├── plugins/                    # 每个 plugin 独立目录
│   ├── keyence-user-manual/
│   │   ├── .claude-plugin/plugin.json
│   │   └── skills/SKILL.md
│   ├── keyence-installation-manual/
│   ├── yokogawa-spec-style/
│   ├── code-review-checklist/
│   └── git-commit-style/
└── README.md
```

---

## 许可

MIT
