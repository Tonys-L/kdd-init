# GitHub Copilot Adapter

复制：

```text
templates/standards/kdd-workflow.md
```

到：

```text
.github/copilot-instructions.md
```

**占位符替换**：将文件中所有 `{{KB_PATH}}` 替换为用户在第一步输入的知识库路径（如 `docs/knowledge-base`）。

> 说明：`.github/copilot-instructions.md` 是 GitHub Copilot Chat 自动识别的自定义指令文件，会自动包含在每个聊天请求中。

---

## 验证

确认以下文件存在：

- `.github/copilot-instructions.md`

在 Copilot Chat 中提问与项目架构相关的问题，验证是否遵循 KDD 工作流。
