# Spec Kit 简体中文 Preset

为 GitHub Spec Kit 提供简体中文（zh-CN）本地化预设。

当前预设以 `specify 1.0.5.dev0` 及更高版本为兼容基线。

## 功能

- `spec.md`、`plan.md`、`tasks.md`、checklist、constitution 等面向人的文档默认使用简体中文。
- `research.md`、`data-model.md`、`quickstart.md` 等由规划流程动态生成的文档同样使用简体中文。
- `/speckit.clarify`、`/speckit.analyze`、`/speckit.implement`、`/speckit.converge` 等流程的人类可读输出使用简体中文。
- 保留机器可读标识和技术协议，例如 `FR-001`、`SC-001`、`US1`、`T001`、`CHK001`、`[P]`、文件路径、代码标识符、HTTP 方法、API 路径等。
- 尽量保持 Spec Kit 官方工作流语义不变，只本地化展示层、文档模板和生成语言。

## 设计原则

> 翻译描述，不翻译协议。

中文用于标题、正文、需求、验收条件、任务描述、解释、分析和面向人的文档内容；英文或原始形式用于代码、路径、稳定标识符、协议、库/框架正式名称以及外部 API。

命令覆盖采用 `wrap` 策略，在官方核心命令外增加中文输出约束，不复制整份核心命令，从而尽量继承 Spec Kit 核心工作流的后续更新。

## 安装

Preset 必须在已经通过 `specify init` 初始化的 Spec Kit 项目中安装。

直接从当前 GitHub 仓库安装：

```bash
specify preset add --from https://github.com/lin52025iq/spec-kit-preset-zh-cn/archive/refs/heads/master.zip
```

安装完成后可以查看状态：

```bash
specify preset list
specify preset info zh-cn
```

## 验证

确认中文模板已经取得解析优先级：

```bash
specify preset resolve spec-template
specify preset resolve plan-template
specify preset resolve tasks-template
specify preset resolve checklist-template
specify preset resolve constitution-template
```

然后运行典型工作流：

```text
/speckit.constitution
/speckit.specify <功能描述>
/speckit.clarify
/speckit.plan
/speckit.tasks
/speckit.analyze
/speckit.implement
/speckit.converge
```

预期生成或更新的人类可读文档内容均为简体中文，包括：

```text
.specify/memory/constitution.md
specs/<feature>/spec.md
specs/<feature>/plan.md
specs/<feature>/research.md
specs/<feature>/data-model.md
specs/<feature>/quickstart.md
specs/<feature>/tasks.md
specs/<feature>/checklists/*.md
```

代码、API、路径以及 `FR-001`、`SC-001`、`US1`、`T001` 等机器可读标识应保持原始形式。

## 更新

当前安装地址跟随仓库 `master` 分支。如需获取仓库中的最新版本，可以先移除已安装 Preset，再使用上面的仓库地址重新安装：

```bash
specify preset remove zh-cn
specify preset add --from https://github.com/lin52025iq/spec-kit-preset-zh-cn/archive/refs/heads/master.zip
```

## 适用范围

这个 Preset 适合希望继续使用官方 Spec Kit SDD 工作流，但要求规格、计划、研究、数据模型、任务、检查清单和项目宪章默认以简体中文呈现的项目。

它不会翻译源代码标识符，也不会修改 Spec Kit 核心流程的业务语义。

## 当前版本

`0.2.0`

- 以 `specify 1.0.5.dev0` 为最低兼容版本。
- 中文化 5 个核心文档模板。
- 为 `specify`、`clarify`、`plan`、`tasks`、`checklist`、`analyze`、`constitution`、`implement`、`converge` 提供中文 `wrap` 包装。
- 补齐当前核心规格模板中的“假设”部分。
