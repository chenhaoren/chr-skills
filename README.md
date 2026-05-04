# chr-skills

Claude Code 个人技能集。涵盖源码分析、Agent 工作流、代码审查、开发计划等场景。

## 技能列表

| 技能 | 类型 | 描述 |
|------|------|------|
| [source-code-analyzer](source-code-analyzer/SKILL.md) | 分析 | 源码阅读拆解：从零理解不熟悉的代码库，分层深入分析项目结构、运行流程与核心设计 |

## 安装

```bash
# 安装全部技能
npx @anthropic-ai/claude-code add chenhaoren/chr-skills

# 安装单个技能
npx @anthropic-ai/claude-code add chenhaoren/chr-skills/<skill-name>
```

## 使用

安装后，在 Claude Code 中通过 `/` 或自然语言触发对应技能：

```
/your-skill-name
"帮我拆解这个项目"
"开始代码审查"
```

## 项目结构

```
chr-skills/
├── README.md
├── .gitignore
├── <skill-name>/
│   ├── SKILL.md          # 技能定义文件（必需）
│   └── ...               # 技能配套资源（可选）
└── <other-assets>/       # agent / hook / 脚本等
    └── ...
```

项目中每个技能独立目录，互不依赖。其他类型资源按用途组织。

## 添加新技能

1. 在根目录下创建 `<skill-name>/SKILL.md`
2. 在 `SKILL.md` 顶部添加 frontmatter：

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
