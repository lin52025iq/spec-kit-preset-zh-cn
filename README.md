# Spec Kit 简体中文 Preset（zh-CN）

为 GitHub Spec Kit 提供简体中文（zh-CN）本地化预设，在尽量保持官方工作流语义不变的前提下，将规格、规划、任务、检查清单、项目宪章以及相关人类可读输出本地化为简体中文。

> 设计原则：**翻译描述，不翻译协议。**

当前预设以 `specify 1.0.5.dev0` 及更高版本为兼容基线。

## 功能

- 将 `spec.md`、`plan.md`、`tasks.md`、checklist、constitution 等核心文档模板本地化为简体中文。
- 约束 `research.md`、`data-model.md`、`quickstart.md` 等规划流程动态生成的文档使用简体中文。
- 为 `/speckit.specify`、`/speckit.clarify`、`/speckit.plan`、`/speckit.tasks`、`/speckit.checklist`、`/speckit.analyze`、`/speckit.constitution`、`/speckit.implement`、`/speckit.converge` 增加简体中文输出约束。
- 保留机器可读标识和技术协议，例如 `FR-001`、`SC-001`、`US1`、`T001`、`CHK001`、`[P]`、文件路径、代码标识符、HTTP 方法、API 路径等。
- 命令覆盖使用 `wrap` 策略，不复制整份核心命令，以尽量继承 Spec Kit 核心工作流的后续更新。

## Installation / 安装

Preset 应在已经通过 `specify init` 初始化的 Spec Kit 项目中安装。

### 安装稳定版本

使用 `v0.0.3` 固定版本归档安装：

```bash
specify preset add --from https://github.com/lin52025iq/spec-kit-preset-zh-cn/archive/refs/tags/v0.0.3.zip
```

固定 tag 的安装方式可以保证同一版本对应不可变的源码快照，也是提交 Spec Kit Community Presets catalog 时使用的下载地址。

### 开发环境安装

如果需要测试仓库中的未发布改动，可以克隆仓库后使用开发模式：

```bash
specify preset add --dev /path/to/spec-kit-preset-zh-cn
```

安装完成后查看状态：

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

## 适合使用的场景

这个 Preset 适合：

- 团队继续使用官方 Spec Kit CLI 和 SDD 工作流，但希望规格与设计文档主要使用简体中文。
- 项目需要中文需求、计划、任务和分析内容，同时保留代码、API、路径和稳定标识符的原始形式。
- 希望通过独立 preset 获得中文体验，而不是维护 Spec Kit 的中文 fork。

## 不适合使用的场景

这个 Preset 不适合：

- 项目要求所有 Spec Kit 产物统一保持英文。
- 需要修改 Spec Kit 核心业务流程、命令行为或脚本实现，而不仅仅是本地化模板和人类可读输出。
- 希望翻译代码标识符、API 字段、文件路径或其他机器可读协议。

## 本地化规则

中文用于标题、正文、需求、验收条件、任务描述、解释、分析和面向人的文档内容。

以下内容保持英文或原始形式：

- 源代码与代码标识符
- 文件路径与命令
- HTTP 方法与 API 路径
- Schema 字段
- 稳定机器标识符，例如 `FR-001`、`SC-001`、`US1`、`T001`
- 库、框架、产品的正式名称

技术术语首次出现时可以采用“中文名称（English Term）”，后续优先使用中文。

## 提供的覆盖

### Templates

- `spec-template`
- `plan-template`
- `tasks-template`
- `checklist-template`
- `constitution-template`

### Commands

- `speckit.specify`
- `speckit.clarify`
- `speckit.plan`
- `speckit.tasks`
- `speckit.checklist`
- `speckit.analyze`
- `speckit.constitution`
- `speckit.implement`
- `speckit.converge`

## 版本与更新

当前版本：`0.0.3`

版本发布遵循语义化版本号。发布新版本时：

1. 更新 `preset.yml` 中的版本号。
2. 更新 `CHANGELOG.md`。
3. 创建对应的 Git tag 和 GitHub Release。
4. 使用对应 tag 的归档 URL 安装和提交 catalog 更新。

## License

MIT
