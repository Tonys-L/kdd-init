# Claude Code Adapter

创建：

```text
CLAUDE.md
```

内容为以下文件的内容：

```text
templates/standards/kdd-workflow.md
```

在文件开头添加：

```text
本项目采用 KDD（Knowledge Driven Development）。

开始任何任务前必须阅读：

- docs/knowledge-base/README.md
- docs/knowledge-base/architecture-overview/
- docs/knowledge-base/development-guide/
- docs/knowledge-base/development-guide/design-principles.md
```

---

## 完整结构

```text
[开头说明]

---

[workflow 内容]
```

---

## 验证

确认 `CLAUDE.md` 文件存在于项目根目录。

在 Claude Code 中提问与项目架构相关的问题，验证是否遵循 KDD 工作流。
