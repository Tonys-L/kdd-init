# ADR Index

## 已采纳决策

| 编号 | 标题 | 业务分类 | 状态 | 影响模块 | 日期 |
|------|------|----------|------|----------|------|
| <!-- ADR-001 --> | <!-- 标题 --> | <!-- 对应 business-capabilities/capabilities.md 中的能力 --> | <!-- Draft/Proposed/Accepted/Deprecated/Superseded --> | <!-- 模块 --> | <!-- YYYY-MM-DD --> |

## ADR 生命周期

```text
Draft → Proposed → Accepted → Deprecated → Superseded
```

## ADR 模板

每个 ADR 文件使用以下结构：

```markdown
# ADR-NNN: 标题

## 状态

[Draft | Proposed | Accepted | Deprecated | Superseded by ADR-XXX]

## 背景

描述驱动此决策的背景和问题。

## 方案选项

### 选项 A

描述。

优点：
- ...

缺点：
- ...

### 选项 B

描述。

优点：
- ...

缺点：
- ...

## 决策

选择了哪个方案，以及为什么。

## 影响

此决策带来的影响和后果。
```

新增 ADR 时：
1. 在 `adr/` 目录下创建文件，命名格式：`NNN-简短标题.md`
2. 编号接续当前最大编号
3. 更新本索引的标题、业务分类、状态、影响模块和日期
4. 填写业务分类（对应 business-capabilities/capabilities.md 中的能力名称）

---

## 变更记录

| 日期 | 变更内容 | 变更人 | 关联变更 |
|------|----------|--------|----------|
| [初始化日期] | 初始版本 | [作者] | — |
