# 实施计划：[功能名称]

**分支**：`[###-feature-name]` | **日期**：[DATE] | **规格**：[link]

**输入**：来自 `/specs/[###-feature-name]/spec.md` 的功能规格。

**说明**：此模板由 `__SPECKIT_COMMAND_PLAN__` 命令填写；具体执行流程以命令定义为准。

## 摘要

[从功能规格中提取主要需求，并结合研究结果说明技术实现方法。]

## 技术上下文

**语言 / 版本**：[例如 Python 3.13、TypeScript 5.x，或 NEEDS CLARIFICATION]

**主要依赖**：[例如 FastAPI、React、PostgreSQL，或 NEEDS CLARIFICATION]

**存储方式**：[例如 PostgreSQL、CoreData、文件，或 N/A]

**测试方案**：[例如 pytest、Vitest、Playwright，或 NEEDS CLARIFICATION]

**目标平台**：[例如 Linux Server、Web Browser、iOS 18+，或 NEEDS CLARIFICATION]

**项目类型**：[例如 library / cli / web-service / mobile-app / desktop-app，或 NEEDS CLARIFICATION]

**性能目标**：[领域相关的可衡量目标，或 NEEDS CLARIFICATION]

**约束条件**：[安全、资源、延迟、离线能力、兼容性等约束，或 NEEDS CLARIFICATION]

**规模 / 范围**：[用户量、数据规模、代码规模、页面数量等，或 NEEDS CLARIFICATION]

## 宪章检查

**门禁**：必须在阶段 0 研究之前通过，并在阶段 1 设计完成后重新检查。

[根据项目 constitution 文件确定并填写门禁要求。]

## 项目结构

### 本功能文档

```text
specs/[###-feature]/
├── plan.md              # 本文件（__SPECKIT_COMMAND_PLAN__ 输出）
├── research.md          # 阶段 0 输出
├── data-model.md        # 阶段 1 输出
├── quickstart.md        # 阶段 1 输出
├── contracts/           # 阶段 1 输出
└── tasks.md             # 阶段 2 输出（由 __SPECKIT_COMMAND_TASKS__ 创建）
```

### 源代码（仓库根目录）

```text
# [未使用则删除] 方案 1：单项目（默认）
src/
├── models/
├── services/
├── cli/
└── lib/

tests/
├── contract/
├── integration/
└── unit/

# [未使用则删除] 方案 2：Web 应用
backend/
├── src/
└── tests/

frontend/
├── src/
└── tests/

# [未使用则删除] 方案 3：移动端 + API
api/
└── [同 backend]

ios/ 或 android/
└── [平台相关结构]
```

**结构决策**：[说明最终采用的项目结构，并引用真实目录。]

## 复杂度跟踪

> 仅当宪章检查存在必须说明的违反项时填写。

| 违反项 | 为什么必须这样做 | 为什么更简单的方案不足 |
|---|---|---|
| [约束] | [当前需求] | [拒绝更简单方案的原因] |
