# Custom Adapter

询问用户：

```text
请输入 Agent 规则目录：

例如：

.ai/rules/

.agent/

.github/

custom/path/
```

---

## 文件格式

询问用户规则文件格式：

```text
请选择规则文件格式：

1. .md（Markdown，直接复制）
2. .mdc（Cursor 格式，需添加 frontmatter）
```

### .md 格式

直接复制，无需修改：

```text
templates/standards/kdd-workflow.md → {用户目录}/kdd-workflow.md
templates/standards/design-principles.md → {用户目录}/design-principles.md
```

### .mdc 格式

复制后需在文件最开头添加 frontmatter：

```yaml
---
description: [规则描述]
alwaysApply: true
---
```

- `kdd-workflow.mdc`：description 填写 "KDD 七步门禁工作流，所有任务必须遵循"
- `design-principles.mdc`：description 填写 "系统架构设计原则，设计决策时必须遵循"

---

## 验证

确认以下文件存在于用户指定目录：

- `{用户目录}/kdd-workflow.md`（或 `.mdc`）
- `{用户目录}/design-principles.md`（或 `.mdc`）

在对应 Agent 中提问与项目架构相关的问题，验证是否遵循 KDD 工作流。
