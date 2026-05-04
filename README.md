# chr-skills

一套 Claude Code 技能集，提升代码分析、开发效率和质量。

## 技能列表

| 技能 | 描述 |
|------|------|
| [source-code-analyzer](source-code-analyzer/SKILL.md) | 源码阅读拆解。从零理解不熟悉的代码库：分层深入分析项目结构、运行流程、核心设计与关键细节，输出可落地的文档 |

## 安装

```bash
# 安装全部技能
npx @anthropic-ai/claude-code add chenhaoren/chr-skills

# 安装单个技能
npx @anthropic-ai/claude-code add chenhaoren/chr-skills/source-code-analyzer
```

## 使用

安装后，在 Claude Code 中说出触发词即可调用对应技能，例如：

> "帮我拆解这个项目"
> "分析一下这个源码的结构"
> "我想理解这个代码库的设计"

## 项目结构

```
chr-skills/
├── README.md
├── .gitignore
└── <skill-name>/
    └── SKILL.md          # 技能定义文件
```

## 开发

### 添加新技能

1. 在根目录下创建 `<skill-name>/SKILL.md`
2. 在 `SKILL.md` 顶部添加 frontmatter：

```yaml
---
name: your-skill-name
description: 简短的技能描述，用于触发匹配
---
```

3. 在 README 技能列表中添加一行

## 许可证

MIT
