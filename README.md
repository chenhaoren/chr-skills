# chr-skills

个人 Claude Code 技能集。包含用于源码分析、开发工作流的可复用技能。

## 技能列表

| 技能 | 描述 |
|------|------|
| [source-code-analyzer](source-code-analyzer/SKILL.md) | 源码阅读拆解：从零理解不熟悉的代码库，分层深入分析项目结构、运行流程、核心设计与关键细节 |

## 安装

通过 Claude Code 的 `skills` CLI 安装全部技能：

```bash
npx @anthropic-ai/claude-code add chenhaoren/chr-skills
```

或只安装单个技能：

```bash
npx @anthropic-ai/claude-code add chenhaoren/chr-skills/source-code-analyzer
```

安装完成后即可通过技能的触发词在 Claude Code 中调用。

## 许可证

MIT
