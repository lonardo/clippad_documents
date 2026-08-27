# Usage Guide / 使用指南

For guided, practical scenarios, see [Try OfficeAddin / 试用场景](try-it.md).

如需按真实任务逐步体验，请阅读[OfficeAddin 试用场景](try-it.md)。

For a visual map of the Ribbon, command editor, context menu, Excel AIGEN, insights, and settings, see [UI Guide / 带图界面指引](ui-guide.md).

如需查看功能区、指令编辑器、上下文菜单、Excel AIGEN、洞察和设置的带图说明，请阅读[界面指引](ui-guide.md)。

## First use / 第一次使用

1. Install the matching signed Release.
2. Reopen Word, Excel, or PowerPoint.
3. Open the Office AI / AI助手 Ribbon tab.
4. Run a read-only context or diagnostic command.
5. Start with a disposable or backed-up document.

安装对应签名 Release 后重新打开 Office，在 Office AI / AI助手功能区中先执行只读上下文或诊断命令，再处理重要文档。

## Recommended action order / 推荐操作顺序

~~~text
Understand the task / 明确任务
    -> inspect current context / 检查当前文档、选区和应用
    -> preview / 预览影响范围、输出路径或写入计划
    -> confirm / 用户确认
    -> backup when needed / 必要时备份
    -> commit / 提交写入
    -> verify and report / 验证结果并返回摘要
~~~

For a write command, a successful-looking UI message is not enough. Confirm the output file, changed sheet/slide/paragraph, result summary, and any failure list.

对于写入命令，不能只看界面提示；还应确认输出文件、修改的工作表/幻灯片/段落、结果摘要和失败清单。

## Word / Word 使用重点

- Select text before selection-oriented actions.
- Use read-only outline, review, and formatting checks before applying changes.
- Preserve document text, facts, fields, comments, and attachments unless the command explicitly targets them.
- Save a copy before large formatting or revision operations.

## Excel / Excel 使用重点

- Select the intended range and check the range summary before processing.
- Confirm headers, row count, formula state, and blank/error state.
- Prefer a new sheet or output file for cleanup, mapping, deduplication, and export.
- Check formulas and external-link warnings before converting values or overwriting cells.

## PowerPoint / PowerPoint 使用重点

- Check the active slide or selected shapes before object operations.
- Preview title, footer, page-number, layout, and text changes.
- Do not copy business content from a sample presentation when only formatting migration is requested.
- Treat master, theme, placeholder, animation, and hidden-slide operations as higher-risk actions.

## Command editor and script library / 指令工厂与脚本库

The command editor is for turning a repeatable manual process into a named command. A good command has one clear goal, explicit inputs, bounded output, a failure result, and a safe write policy.

指令工厂用于把可重复的手工流程沉淀成命名命令。一个好的命令应有明确目标、明确输入、受控输出、失败结果和安全写入策略。

For public VBS functions, use the community repository:

https://github.com/lonardo/clippad_functions

The public VBS library is Host-first. Do not add arbitrary shell, registry, filesystem, or hidden Office process creation to a command.

## AI-assisted actions / AI 辅助操作

Before sending an AI request:

- confirm the selected text and document context;
- remove confidential content when it is not necessary;
- state the desired output and Office application;
- review the generated command before execution;
- use preview and confirmation for document writes.

调用 AI 前请确认选区和上下文、删除不必要的敏感内容、说明目标应用和输出格式，并在执行生成命令前检查代码；写入文档必须经过预览和确认。

## Cancel, rollback, and recovery / 取消、回滚与恢复

Cancel a plan before commit when the preview is wrong. After a write, use the product history/undo path or restore the backup created by the command. If a script does not expose a clear recovery path, do not use it on the original document.

预览不正确时应在提交前取消；写入后使用产品历史/撤销能力或恢复命令生成的备份。没有明确恢复路径的脚本不要直接用于原始文档。
