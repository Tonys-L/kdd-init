# Cursor Adapter

创建：

```text
.cursor/rules/
```

---

复制：

```text
templates/standards/kdd-workflow.md
```

到：

```text
.cursor/rules/kdd-workflow.mdc
```

**占位符替换**：将文件中所有 `{{KB_PATH}}` 替换为用户在第一步输入的知识库路径（如 `docs/knowledge-base`）。

在文件**最开头**添加以下 frontmatter：

```yaml
---
description: KDD 七步门禁工作流，所有任务必须遵循
alwaysApply: true
---
```

---

## Frontmatter 说明

| 字段 | 说明 |
|------|------|
| `description` | 规则文件的描述，Cursor 用于判断是否加载 |
| `alwaysApply` | 是否始终加载，KDD 规则需要始终生效 |

如果项目较大，希望规则仅在特定文件时加载，可设置 `alwaysApply: false` 并添加 `globs`：

```yaml
---
description: KDD 七步门禁工作流
globs: ["src/**/*"]
alwaysApply: false
---
```

---

## 验证

确认以下文件存在且包含 frontmatter：

- `.cursor/rules/kdd-workflow.mdc`

在 Cursor Chat 中提问与项目架构相关的问题，验证是否遵循 KDD 工作流。
