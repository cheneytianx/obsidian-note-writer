# Frontmatter 规范

## 基础 Frontmatter（所有笔记必须有）

```yaml
---
tags: [tag1, tag2]
created: YYYY-MM-DD
source: conversation
---
```

## source 字段取值

| 值 | 含义 |
|----|------|
| `conversation` | 从对话总结生成 |
| `manual` | 用户手动创建/口述 |
| `paper` | 论文阅读笔记 |
| `web` | 网页内容整理 |
| `book` | 读书笔记 |
| `meeting` | 会议记录 |

## 扩展字段（按需添加）

```yaml
---
tags: [ai, security, memory-poisoning]
created: 2026-05-09
source: paper
aliases: [MemoryGraft, memory graft]   # 别名，方便双链搜索
paper_url: https://arxiv.org/abs/2512.16962
author: Srivastava, He
status: reading   # reading / done / review
---
```

## Tags 命名规范

- 全小写，单词间用连字符：`machine-learning` ✅，`MachineLearning` ❌
- 具体优于宽泛：`memory-poisoning` > `security` > `tech`
- 每篇笔记 2~5 个 tag 为宜
- 层级 tag 用斜线：`ai/llm`、`security/agent`

## 常用 Tags 参考

```
技术类: llm, agent, security, backend, frontend, infra, database
学习类: reading, paper, concept, tutorial
工作类: meeting, project, decision, todo
状态类: stub, wip, done, archive
```
