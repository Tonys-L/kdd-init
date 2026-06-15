# Knowledge Base

本目录存放项目知识库。

知识库用于记录项目事实、业务知识、架构设计、领域模型、技术决策和历史经验。

---

# 核心文档

## business-capabilities.md

业务背景、核心业务能力、业务边界、业务流程。

适用于理解：

* 系统解决什么问题
* 系统提供哪些能力
* 能力之间如何协作
* 能力边界在哪里

---

## domain-model.md

领域模型定义。

包含：

* 实体（Entity）
* 值对象（Value Object）
* 枚举（Enum）
* 领域事件（Domain Event）
* 业务不变量（Invariant）

适用于理解：

* 核心业务对象
* 对象关系
* 业务规则

---

## architecture-overview.md

系统架构设计。

包含：

* 系统结构
* 模块职责
* 依赖关系
* 数据流向
* 扩展点

适用于理解：

* 系统如何组织
* 模块如何协作
* 依赖方向

---

## development-guide.md

工程开发规范。

包含：

* 项目结构
* 编码规范
* 测试规范
* 工程约定

适用于理解：

* 如何开发
* 如何测试
* 如何组织代码

---

## data-model.md

数据模型设计。

包含：

* 数据结构
* 存储模型
* 表结构
* 索引设计

适用于理解：

* 数据如何组织
* 数据如何存储
* 数据如何关联

---

## project-context.md

项目上下文。

包含：

* 项目目标
* 当前阶段
* 已知约束
* 已知未来规划

适用于理解：

* 项目解决什么问题
* 项目处于什么阶段
* 有哪些约束条件

---

## glossary.md

术语表。

包含：

* 业务术语
* 技术术语
* 缩写定义

适用于统一项目语言。

---

# 条件文档

根据项目特点按需创建。

---

## service-specs.md

服务规格说明。

包含：

* 领域服务
* 状态机
* 跨实体流程
* 业务编排逻辑

适用于复杂业务流程场景。

---

## api-contracts.md

API 契约定义。

包含：

* HTTP API
* 请求模型
* 响应模型
* 错误码定义
* 兼容性约束

适用于对外接口场景。

---

## protocol-docs.md

协议定义。

包含：

* MQTT
* WebSocket
* TCP/UDP
* 自定义协议

适用于实时通信场景。

---

# ADR

目录：

```text
adr/
```

用于记录重要架构决策。

每个 ADR 应描述：

* 背景
* 方案
* 决策
* 影响

详见：

```text
adr/README.md
```

---

# Traceability

目录：

```text
traceability/
```

用于追踪：

* 需求与业务分类的映射
* 需求与 ADR 的映射
* ADR 与代码模块的映射

详见：

```text
traceability/README.md
```

---

# Lessons Learned

目录：

```text
lessons/
```

用于记录：

* Bug 复盘
* 线上事故
* 设计失误
* 性能问题
* 实践经验

帮助项目持续积累经验并避免重复踩坑。
