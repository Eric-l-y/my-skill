---
name: git-commit-style
description: Git 提交信息规范。当用户说"commit"、"提交"、"提交代码"时触发，生成规范的 commit message。
---

# Git 提交信息规范

根据当前 staged 的变更，生成符合 Conventional Commits 规范的提交信息。

## 格式

```
<type>(<scope>): <subject>

[body]

[footer]
```

## Type 类型

| Type | 说明 | 示例 |
|------|------|------|
| `feat` | 新功能 | `feat(auth): 添加微信登录` |
| `fix` | 修复 bug | `fix(api): 修复分页参数校验` |
| `docs` | 文档变更 | `docs: 更新 README 安装步骤` |
| `style` | 代码格式（不影响逻辑） | `style: 统一缩进为 2 空格` |
| `refactor` | 重构（既非新功能也非修复） | `refactor(utils): 提取公共验证函数` |
| `perf` | 性能优化 | `perf(query): 添加数据库索引` |
| `test` | 测试相关 | `test(auth): 补充登录模块单元测试` |
| `chore` | 构建/工具/依赖变更 | `chore: 升级 webpack 到 v5` |
| `ci` | CI/CD 配置 | `ci: 添加 GitHub Actions 发布流程` |

## 规则

1. subject 不超过 50 个字符
2. subject 用中文或英文，保持项目一致
3. subject 不用大写开头，不加句号
4. body 说明「为什么」改，而非「改了什么」
5. 一个 commit 只做一件事

## 执行流程

1. 运行 `git diff --cached` 查看 staged 变更
2. 分析变更内容，确定 type 和 scope
3. 生成 commit message
4. 展示给用户确认
5. 用户确认后执行 `git commit`
