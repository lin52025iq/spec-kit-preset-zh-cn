# Spec Kit 简体中文 Preset

为 GitHub Spec Kit 提供简体中文（zh-CN）本地化预设。

## 目标

- `spec.md`、`plan.md`、`tasks.md`、checklist、constitution 等面向人的文档默认使用简体中文。
- `research.md`、`data-model.md`、`quickstart.md` 等由规划流程动态生成的文档同样使用简体中文。
- 保留机器可读标识和技术协议，例如 `FR-001`、`SC-001`、`US1`、`T001`、`CHK001`、文件路径、代码标识符、HTTP 方法、API 路径等。
- 尽量保持 Spec Kit 官方工作流语义不变，只本地化展示层与生成语言。

## 设计原则

> 翻译描述，不翻译协议。

中文用于标题、正文、需求、验收条件、任务描述、解释和分析；英文或原始形式用于代码、路径、标识符、协议、库/框架正式名称以及外部 API。

命令覆盖采用 `wrap` 策略，在官方核心命令外增加中文输出约束，因此无需复制整份核心命令，能够更好继承未来 Spec Kit 的工作流更新。

## 本地开发

```bash
specify preset add --dev .
```

验证模板解析：

```bash
specify preset resolve spec-template
specify preset resolve plan-template
specify preset resolve tasks-template
specify preset resolve checklist-template
specify preset resolve constitution-template
```

然后在测试项目中运行：

```text
/speckit.constitution
/speckit.specify <功能描述>
/speckit.clarify
/speckit.plan
/speckit.tasks
/speckit.analyze
```

## 当前版本

`0.1.0`：第一版中文模板与核心命令中文输出约束。
