# KDD Init

Knowledge Driven Development（知识库驱动开发）初始化工具。

让 AI 编码助手基于项目知识库工作，而不是基于猜测。

## 为什么需要 KDD

AI 编码助手在没有项目上下文的情况下，容易：

- 猜测业务规则，写出不符合需求的代码
- 无视现有架构，随意引入新模式
- 重复踩坑，不吸取项目历史教训
- 修改代码后不更新文档，知识逐渐失真

KDD 通过建立项目知识库，让 AI 在每次任务前先阅读知识、理解设计、分析影响，再动手编码。

## 核心理念

```text
知识库驱动开发
设计先于编码
文档先于实现
测试保证质量
代码与知识同步
设计与实现一致
```

## 工作流程

所有任务必须经过七步门禁：

```text
知识库阅读 → 影响分析 → 设计方案 → 用户确认 → 开发实现 → 测试验证 → 知识库同步
```

纯 UI 调整可走轻量门禁，走简化流程。

## 快速开始

### 1. 安装 Skill

将本项目作为 Skill 安装到你的 AI 编码工具中。

### 2. 执行初始化

运行 `kdd-init` Skill，按提示操作：

1. 创建知识库目录
2. 选择你使用的 Agent（Trae / Cursor / Claude Code / GitHub Copilot / Custom）
3. 加载对应 Agent 适配器
4. AI 自动分析代码，生成知识库文档
5. 完成初始化

### 3. 开始开发

初始化完成后，AI 会自动遵循 KDD 工作流：每次任务前先读知识库，分析影响，设计方案，获得确认后再编码。

## 项目结构

```text
kdd-init/
├── SKILL.md                          # Skill 入口
├── adapters/                         # 多 Agent 适配
│   ├── trae.md                       #   Trae
│   ├── cursor.md                     #   Cursor
│   ├── claude.md                     #   Claude Code
│   ├── copilot.md                    #   GitHub Copilot
│   └── custom.md                     #   自定义
└── templates/
    ├── standards/                    # AI 规则文件
    │   └── kdd-workflow.md           #   七步门禁工作流
    └── knowledge-base/               # 知识库模板
        ├── README.md                 #   知识库导航
        ├── project-context/          #   项目上下文（核心）
        │   ├── README.md             #     TL;DR + 索引
        │   ├── goals.md              #     项目目标
        │   ├── constraints.md        #     已知约束
        │   └── roadmap.md            #     未来规划
        ├── business-capabilities/    #   业务能力（核心）
        │   ├── README.md             #     TL;DR + 索引
        │   ├── background.md         #     业务背景
        │   ├── capabilities.md       #     核心能力
        │   ├── boundaries.md         #     能力边界
        │   └── flows.md              #     业务流程
        ├── domain-model/             #   领域模型（核心）
        │   ├── README.md             #     TL;DR + 索引
        │   ├── entities.md           #     实体
        │   ├── value-objects.md      #     值对象
        │   ├── invariants.md         #     不变量（必读）
        │   └── events.md             #     领域事件
        ├── architecture-overview/    #   架构总览（核心）
        │   ├── README.md             #     TL;DR + 索引
        │   ├── layers.md             #     分层结构
        │   ├── dependencies.md       #     依赖规则
        │   └── data-flows.md         #     数据流向
        ├── development-guide/        #   开发规范（核心）
        │   ├── README.md             #     TL;DR + 索引
        │   ├── design-principles.md  #     设计原则
        │   ├── code-standards.md     #     代码规范
        │   ├── architecture-rules.md #     架构规范
        │   └── testing.md            #     测试规范
        ├── data-model/               #   数据模型（核心）
        │   ├── README.md             #     TL;DR + 索引
        │   ├── tables.md             #     表结构
        │   └── migration.md          #     迁移策略
        ├── glossary.md               #   术语表（核心，单文件）
        ├── service-specs/            #   服务规格（条件）
        │   ├── README.md             #     TL;DR + 索引
        │   ├── services.md           #     服务定义
        │   └── state-machines.md     #     状态流转
        ├── api-contracts/            #   API 契约（条件）
        │   ├── README.md             #     TL;DR + 索引
        │   ├── endpoints.md          #     接口定义
        │   └── errors.md             #     错误码
        ├── protocol-docs/            #   协议文档（条件）
        │   ├── README.md             #     TL;DR + 索引
        │   └── messages.md           #     消息定义
        ├── adr/                      #   架构决策记录
        ├── traceability/             #   需求追踪矩阵
        └── lessons/                  #   经验教训库
```

### 文档分类

**核心文档**：所有项目都需要，初始化时自动生成。

**条件文档**：按项目特点按需创建：

| 文档 | 适用场景 |
|------|---------|
| service-specs/ | 复杂业务流程、状态机 |
| api-contracts/ | 对外 HTTP 接口 |
| protocol-docs/ | MQTT/WebSocket 等实时通信 |

**积累文档**：初始化时创建空目录，随项目演进持续积累：

| 文档 | 用途 |
|------|------|
| adr/ | 架构决策记录，做出重要技术决策时新增 |
| traceability/ | 需求追踪矩阵，新增需求/ADR 时更新 |
| lessons/ | 经验教训库，踩坑/复盘时新增 |

## 支持的 Agent

| Agent | 规则目录 | 说明 |
|-------|---------|------|
| Trae | `.trae/rules/` | 直接复制 |
| Cursor | `.cursor/rules/` | 后缀改为 .mdc |
| Claude Code | `CLAUDE.md` | 合并为单文件 |
| GitHub Copilot | `.github/copilot-instructions.md` | 重命名文件 |
| Custom | 用户指定 | 直接复制 |

## 设计原则

KDD 遵循 6 条设计原则：

1. **业务优先** — 从业务能力出发设计，而非从数据库、框架、技术栈出发
2. **职责优先** — 每个模块拥有明确职责，高内聚低耦合
3. **三层隔离** — 策略层（易变）→ 核心层（稳定）← 技术层（可替换）。逻辑分层，业务内聚、变更隔离、依赖单向
4. **避免过度设计** — Simple First, Evolve Later
5. **变更成本** — 为已知变化设计，不为未知变化设计
6. **按变化演进** — 解决问题 → 发现变化 → 抽象能力 → 沉淀扩展点 → 持续演进

原则冲突时按优先级裁决：业务优先 > 职责优先 > 变更成本 > 简单优先 > 扩展优先

## License

MIT
