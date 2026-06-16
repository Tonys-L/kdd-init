# 代码规范

## 命名规范

| 类型 | 规范 | 示例 |
|------|------|------|
| 文件/目录 | kebab-case | `user-service.ts` |
| 类/接口 | PascalCase | `UserService` |
| 函数/方法 | camelCase | `getUserById()` |
| 常量 | UPPER_SNAKE_CASE | `MAX_RETRY_COUNT` |
| 枚举值 | PascalCase | `UserStatus.Active` |
| 布尔变量 | is/has/can 前缀 | `isActive`, `hasPermission` |

---

## 文件组织

<!-- 描述项目的目录结构和文件组织方式，例如：
src/
├── modules/           # 业务模块
│   └── user/          # 按业务能力组织
│       ├── user-service.ts
│       ├── user-service.test.ts
│       └── types.ts
├── shared/            # 共享模块
│   ├── types/         # 公共类型
│   └── utils/         # 工具函数
└── technology/        # 技术层
-->

---

## 导入顺序

```typescript
// 1. 外部库
// 2. 内部类型
// 3. 内部模块
// 4. 相对路径
```

---

## 代码风格

- 单个函数不超过 30 行，超过则拆分
- 单个文件不超过 300 行，超过则拆分职责
- 嵌套不超过 3 层，超过则提取函数
- 参数不超过 4 个，超过则使用对象参数
- 禁止魔法数字，必须提取为命名常量
- 优先使用 `const`，仅在需要重赋值时使用 `let`，禁止 `var`

---

## 注释规范

- 公共 API 必须有文档注释
- 复杂业务逻辑必须有行内注释说明意图
- 禁止无意义注释（如 `// set name` 在 `setName()` 上方）
- TODO 必须附带日期和负责人：`// TODO(姓名 2024-01-01): 描述`

---

## 变更记录

| 日期 | 变更内容 | 变更人 | 关联变更 |
|------|----------|--------|----------|
| [初始化日期] | 初始版本 | [作者] | — |
