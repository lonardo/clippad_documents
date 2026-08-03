# AI-assisted VBS Generation / 大模型生成 VBS 指南

This guide describes the public, reproducible way to ask an AI model to generate or repair a VBS function for OfficeAddin. It does not publish private model endpoints, credentials, customer prompts, or backend implementation.

本文档描述如何用可复现方式让大模型生成或修复 OfficeAddin VBS，不公开私有模型接口、凭据、客户提示词或后端实现。

## Required inputs / 必需输入

Provide the model with:

1. the current Host API JSON;
2. the public system prompt;
3. the target Office application;
4. the current document and selection state;
5. input, output, risk, preview, confirmation, and rollback requirements;
6. one reviewed VBS example from the same category;
7. acceptance cases and a failure example.

生成时必须提供：Host API JSON、公共系统提示词、目标 Office 应用、当前文档/选区状态、输入输出及风险要求、同类已审查 VBS 示例、验收案例和失败案例。

Public sources:

~~~text
https://github.com/lonardo/clippad_functions/blob/main/prompts/vbs-system-prompt.md
https://raw.githubusercontent.com/lonardo/clippad_functions/main/host/host-api-v1.json
~~~

## Prompt layers / 提示词分层

~~~text
System rules
  -> Host API v1 contract
  -> target app and risk policy
  -> task-specific input/output
  -> reviewed example
  -> acceptance tests
~~~

Do not put a long private conversation history into every generation request. Keep the Host contract and safety rules stable, and pass only the task context needed for the current function.

不要把完整私聊历史放入每次生成请求；保持 Host 契约和安全规则稳定，只传当前函数真正需要的任务上下文。

## Required generated shape / 生成结果要求

Every generated public function should:

- use Function Main();
- keep UTF-8 BOM in the source file;
- use only Host methods in the public manifest;
- distinguish read-only, preview, write, and destructive actions;
- return a small JSON result;
- check app, document, selection, saved state, and output path;
- preview and confirm before writes;
- provide backup or rollback behavior;
- avoid CreateObject, GetObject, WScript.Shell, Shell.Application, ADODB.Stream, FileSystemObject, InputBox, MsgBox, registry, shell, and hidden Office process creation.

每个公共生成函数都应满足以上要求，不能仅因为代码“能运行”就跳过预览、确认和恢复设计。

## Host.GetSelection decision / Host.GetSelection 选择规则

- Use Host.GetSelection() for current selection text only.
- Use Host.GetSelectionInfo() for structured selection metadata.
- Use Host.GetSelectionObject() for object-level Office automation.
- Use Host.SelectRange() only when a new interactive selection is required.

Host.GetSelection() does not ask the user to select again. It may return empty text for unsupported or empty selections, and Excel multi-cell arrays are not guaranteed to be expanded.

## Batch generation and repair / 批量生成与修复

~~~text
Task catalog
  -> assign app/category/risk
  -> generate one candidate
  -> validate metadata, Host calls, encoding, and unsafe API
  -> run fake Host/cscript smoke
  -> review preview and rollback
  -> repair only failed candidate
  -> run staging Office smoke
  -> record version and release evidence
~~~

For a batch repair, keep the original file, generated diff, model name/version, prompt version, Host API version, test result, and human decision. Do not silently rewrite every script when only one case failed.

批量修复必须保留原文件、生成 diff、模型版本、提示词版本、Host API 版本、测试结果和人工决定。单个案例失败时不要静默重写全部脚本。

## Review checklist / 审查清单

- Is the target application correct?
- Does the script use the current selection or ask for a new one correctly?
- Are all Host methods in host-api-v1.json?
- Can a user preview the impact?
- Can the user cancel before commit?
- Does the script avoid overwriting the source by default?
- Are logs and returned JSON bounded and redacted?
- Did the test run on the claimed Office version?

## What AI must not do / 大模型不得做什么

The model must not invent a Host method, expose a private endpoint, request a token, claim unsupported Office/Windows versions, publish a Release, change the production upgrade manifest, or commit private documents.

大模型不得虚构 Host 方法、暴露私有接口、索取令牌、声称未经测试的 Office/Windows 支持、发布 Release、修改生产升级清单或提交私有文档。
