---

name: "kdd-init"
description: "初始化知识库驱动开发（KDD）项目结构"
version: "2.0.0"

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

知识库聚焦代码无法表达的内容：约束、不变量、边界和术语。

优先填充核心文档：

```text
README.md         # 项目概览（系统定位、核心业务关系、项目阶段）（必填）
constraints.md    # 约束、不变量、禁止事项（必填）
glossary.md       # 术语表（必填）
```

根据项目需要判断是否创建条件文档：

```text
boundaries.md     # 能力边界（系统与外部有复杂交互时创建）
flows.md          # 业务流程与状态机（存在复杂流程/状态机时创建）
```

### 架构状态检测与文档策略

分析代码结构，判断三层隔离实施状态，填入 `constraints.md` 架构状态字段：

| 架构状态 | 判断依据 | 文档填充深度 |
|----------|----------|-------------|
| 已实施 | 核心层无技术依赖，业务规则内聚 | 只填充负空间（不变量、禁止事项、边界） |
| 部分实施 | 部分模块已隔离，部分混合 | 已隔离模块只填充负空间；未隔离模块补充模块定位表 |
| 未实施 | 业务逻辑与技术实现混合 | 补充模块定位表（模块职责、业务规则位置） |

架构状态不是用户手动选择的，而是 AI 从代码结构中推断的。

### 填充原则

- 从代码中提取项目概览（系统定位、核心业务关系、项目阶段）
- 从代码中提取架构约束（分层规则、依赖方向、模块边界）
- 从代码中提取业务不变量（校验规则背后的业务原因）
- 从代码中提取禁止事项（代码中不存在但不应存在的模式）
- 无法从代码推断的内容保留占位符，提醒用户补充
- 数据结构、API 定义、表结构等代码已表达的内容不写入文档

如果项目代码为空（新项目），则提醒用户优先填写 README.md 项目概览和 constraints.md。

---

## 第五步：完成初始化

输出创建结果和知识库填充情况。

---

### 质量检查

生成知识库后，必须执行以下初始化检查：

```text
□ README.md 项目概览是否已填写系统定位、核心业务关系、项目阶段
□ constraints.md 是否已填写架构状态（从代码结构推断）
□ constraints.md 架构状态为"未实施"或"部分实施"时，是否已填写模块定位表
□ constraints.md 是否已填写架构约束和业务不变量
□ glossary.md 是否已定义核心术语
□ 条件文档是否已根据项目需要判断创建
□ 各文档变更记录是否已填写初始化日期
```

文档间引用有效性、代码与文档一致性等持续健康度检查，详见 `{{KB_PATH}}/README.md` 中的健康度检查清单。

输出检查结果：

```text
【初始化结果】

知识库路径：{父目录}knowledge-base/

已创建文件：
- {父目录}knowledge-base/constraints.md
- {父目录}knowledge-base/glossary.md
- {父目录}knowledge-base/adr/README.md
- {父目录}knowledge-base/lessons/README.md
- ...

已填充内容：
- README.md 项目概览: [已填写 / 部分填写 / 仅占位符]
- constraints.md: [已填写 / 部分填写 / 仅占位符]
- glossary.md: [已填写 / 部分填写 / 仅占位符]
- boundaries.md: [已创建 / 未创建]
- flows.md: [已创建 / 未创建]

质量检查：
- [通过项] / [未通过项]

待用户补充：
- README.md 项目概览中的 [具体占位符]
- constraints.md 中的 [具体占位符]
- glossary.md 中的 [具体占位符]
```
