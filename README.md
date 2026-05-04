# chr-skills

[![skills.sh](https://skills.sh/b/chenhaoren/chr-skills)](https://skills.sh/chenhaoren/chr-skills)

Claude Code 个人技能集。涵盖源码分析、Agent 工作流、代码审查、开发计划等场景。

## 技能列表

| 技能 | 类型 | 描述 |
|------|------|------|
| [source-code-analyzer](source-code-analyzer/SKILL.md) | 分析 | 源码阅读拆解：从零理解不熟悉的代码库，分层深入分析项目结构、运行流程与核心设计 |

---

## 安装

### 方式一：通过 GitHub 安装（推荐）

```bash
# Claude Code
npx @anthropic-ai/claude-code add chenhaoren/chr-skills

# 或使用通用 skills CLI
npx skills add chenhaoren/chr-skills
```

安装单个技能：

```bash
npx @anthropic-ai/claude-code add chenhaoren/chr-skills/source-code-analyzer
```

### 方式二：从指定分支安装

适用场景：想体验开发中的功能、测试 PR、或使用某个历史版本。

```bash
# 从指定分支安装全部技能
npx @anthropic-ai/claude-code add chenhaoren/chr-skills#branch-name

# 从指定分支安装单个技能
npx @anthropic-ai/claude-code add chenhaoren/chr-skills/source-code-analyzer#branch-name

# 示例：从 dev 分支安装
npx @anthropic-ai/claude-code add chenhaoren/chr-skills#dev

# 示例：从 feature 分支安装
npx @anthropic-ai/claude-code add chenhaoren/chr-skills#feat-new-skill
```

> `#` 后面跟分支名，与 GitHub 的 URL 片段标识符语法一致。

### 方式三：从源码安装

适用场景：想自己修改技能、调试、或离线使用。

```bash
# 1. 克隆仓库
git clone https://github.com/chenhaoren/chr-skills.git
cd chr-skills

# 2. 安装到 Claude Code（会复制技能到系统 skills 目录）
npx @anthropic-ai/claude-code add ./source-code-analyzer

# 3. 或在会话中直接引用目录（不安装，仅当前会话可用）
npx @anthropic-ai/claude-code --add-dir ./source-code-analyzer

# 4. 或做软链接到 Claude Code 的 skills 目录，修改即生效
ln -s "$PWD"/source-code-analyzer ~/.claude/skills/source-code-analyzer
```

> **软链接方式的好处**：修改本地的 `SKILL.md` 后，下次使用 Claude Code 会自动生效，适合技能开发和调试。

---

## 使用

技能安装后有两种触发方式：

### 1. 斜杠命令

在 Claude Code 中直接输入：

```
/source-code-analyzer
```

Claude 会加载对应技能的指令。

### 2. 自然语言触发

说出技能的触发场景，Claude 会自动匹配：

```
"帮我拆解这个项目"
"分析一下这个源码的结构"
"这个代码库是怎么实现的"
```

每个技能在 `SKILL.md` 的 `description` 字段定义了触发关键词，Claude 会根据上下文自动匹配合适的技能。

### 3. 查看已安装的技能

```bash
# 列出所有已安装技能
ls ~/.claude/skills/

# 查看当前 Claude Code 支持哪些技能
npx @anthropic-ai/claude-code agents
```

---

## 项目结构

```
chr-skills/
├── README.md               # 项目说明
├── .gitignore
├── <skill-name>/
│   ├── SKILL.md            # 技能定义文件（必需）
│   └── ...                 # 配套资源（可选）
└── <other-assets>/         # agent / hook / 脚本等
    └── ...
```

每个技能独立目录，互不依赖。非 skill 资源按用途组织。

---

## 添加新技能

1. 创建 `<skill-name>/SKILL.md`
2. 顶部添加 frontmatter：

```yaml
---
name: your-skill-name
description: 简短的技能描述，用于触发匹配
---
```

3. 在 README 技能列表中添加一行

> 技能类型不限 — 可以是代码分析、Agent 行为编排、工作流自动化、提示词库等各种用途。

## 许可证

MIT
