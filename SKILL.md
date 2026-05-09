---
name: obsidian-note-writer
description: 将对话内容、知识总结、研究笔记等写入 Obsidian vault（本地 Markdown 文件）。支持自动提取双链关键词、生成 frontmatter、按话题组织文件目录。当用户说"存到 Obsidian"、"生成 Obsidian 笔记"、"记录到知识库"时触发。
---

# Obsidian Note Writer

将对话或知识写入结构化的 Obsidian Markdown 笔记。

## Vault 根目录

默认路径：`~/obsidian-vault`（如用户未指定则询问一次，记住后续复用）。
写文件前用 `ls` 确认目录存在；不存在则创建。

## 文件组织规则

参考 `references/taxonomy.md` 决定存放位置和命名。

核心原则：
- **路径即语义**：目录名表达话题，文件名表达主题，不用编号前缀
- **扁平优先**：目录层级 ≤ 3，过深则重构
- **中英均可**：与用户笔记风格保持一致

## 笔记生成流程

1. **确定话题分类** → 参考 taxonomy.md 选目录
2. **提取双链关键词** → 参考 `references/wikilinks.md`
3. **生成 frontmatter** → 参考 `references/frontmatter.md`
4. **写入正文** → 参考 `references/note-templates.md` 选模板
5. **写文件** → 用 `write` 工具写入，告知完整路径

## 双链提取（核心）

识别内容中的关键概念并用 `[[...]]` 标注。详见 `references/wikilinks.md`。

快速判断：该词是否值得独立成一篇笔记？是 → 加双链。

## Frontmatter 规范

每篇笔记必须包含：

```yaml
---
tags: [tag1, tag2]
created: YYYY-MM-DD
source: conversation  # conversation / manual / web / paper
---
```

详见 `references/frontmatter.md`。

## 完成后告知用户

写入成功后，输出：
- 完整文件路径
- 提取的双链列表（方便用户知道哪些概念值得补充）
- 如有新建目录，说明原因
