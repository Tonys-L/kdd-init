---

name: "kdd-init"
description: "Initialize Knowledge Driven Development (KDD) project structure."
-------------------------------------------------------------------------------

# KDD Init

初始化 Knowledge Driven Development（KDD）项目结构。

## 第一步：创建知识库

创建：

```text
docs/knowledge-base/
```

复制：

```text
templates/knowledge-base/*
```

到：

```text
docs/knowledge-base/
```

---

## 第二步：选择 Agent

询问用户：

```text
请选择当前使用的 Agent：

1. Trae
2. Cursor
3. Claude Code
4. GitHub Copilot
5. Custom
```

---

## 第三步：加载 Adapter

根据用户选择：

读取：

```text
adapters/{agent}.md
```

按照其中定义执行。

---

## 第四步：分析代码，生成知识库

分析项目代码，尽可能自动填充知识库文档。

优先填充核心文档：

```text
project-context.md

business-capabilities.md

domain-model.md

architecture-overview.md
```

根据代码实际情况继续填充：

```text
development-guide.md

data-model.md

glossary.md
```

如果项目存在对应场景，继续填充条件文档：

```text
service-specs.md

api-contracts.md

protocol-docs.md
```

无法从代码推断的内容保留占位符，提醒用户补充。

如果项目代码为空（新项目），则提醒用户优先填写核心文档。

---

## 第五步：完成初始化

输出创建结果和知识库填充情况。
