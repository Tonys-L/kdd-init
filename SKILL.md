---

name: "kdd-init"
description: "初始化知识库驱动开发（KDD）项目结构"
version: "1.0.0"

---

# KDD Init

初始化 Knowledge Driven Development（KDD）项目结构。

## 第一步：确定知识库路径并创建

询问用户：

```text
请输入知识库的父目录（knowledge-base/ 将创建在此目录下）：

例如：

docs/          → docs/knowledge-base/
src/           → src/knowledge-base/
（留空）        → knowledge-base/

默认：docs/
```

根据用户输入，知识库路径为：

```text
{父目录}knowledge-base/
```

后续步骤中所有 `{{KB_PATH}}` 占位符均替换为此路径。

---

创建知识库目录：

```text
{父目录}knowledge-base/
```

复制：

```text
templates/knowledge-base/*
```

到：

```text
{父目录}knowledge-base/
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
adapters/trae.md        # 1. Trae
adapters/cursor.md      # 2. Cursor
adapters/claude.md      # 3. Claude Code
adapters/copilot.md     # 4. GitHub Copilot
adapters/custom.md      # 5. Custom
```

按照其中定义执行。

---

## 第四步：分析代码，生成知识库

分析项目代码，尽可能自动填充知识库文档。

优先填充核心文档：

```text
project-context/
business-capabilities/
domain-model/
architecture-overview/
```

根据代码实际情况继续填充：

```text
development-guide/
data-model/
glossary.md
```

如果项目存在对应场景，继续填充条件文档：

```text
service-specs/
api-contracts/
protocol-docs/
```

无法从代码推断的内容保留占位符，提醒用户补充。

如果项目代码为空（新项目），则提醒用户优先填写核心文档。

---

## 第五步：完成初始化

输出创建结果和知识库填充情况。

---

### 质量检查

生成知识库后，必须执行以下初始化检查：

```text
□ project-context/ 是否已填写项目目标和当前阶段
□ business-capabilities/ 是否已识别核心业务能力
□ domain-model/ 是否已定义核心实体
□ architecture-overview/ 是否已描述分层结构
□ 各文档变更记录是否已填写初始化日期
```

文档间引用有效性、代码与文档一致性等持续健康度检查，详见 `{{KB_PATH}}/README.md` 中的健康度检查清单。

输出检查结果：

```text
【初始化结果】

知识库路径：{父目录}knowledge-base/

已创建文件：
- {父目录}knowledge-base/project-context/README.md
- {父目录}knowledge-base/project-context/goals.md
- ...

已填充内容：
- project-context/: [已填写 / 部分填写 / 仅占位符]
- business-capabilities/: [已填写 / 部分填写 / 仅占位符]
- ...

质量检查：
- [通过项] / [未通过项]

待用户补充：
- project-context/goals.md 中的 [具体占位符]
- domain-model/invariants.md 中的 [具体占位符]
```
