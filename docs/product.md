# Product Overview / 产品介绍

## What OfficeAddin is / OfficeAddin 是什么

OfficeAddin is a Windows desktop COM add-in that integrates with Word, Excel, and PowerPoint. It places command editing, reusable workflows, a script library, intelligent suggestions, and preview-oriented actions inside the Office Ribbon.

OfficeAddin 是集成 Word、Excel 和 PowerPoint 的 Windows 桌面 COM 插件，把指令编辑、可复用工作流、脚本库、智能建议和预览型操作放入 Office 功能区。

The product is designed for users who repeatedly clean, format, compare, summarize, export, or standardize Office documents.

产品主要服务于反复进行文档清理、排版、核对、摘要、导出和规范化的用户。

See [Product Design / 产品设计](product-design.md) for the principles behind commands, insights, and the AI workbench.

如需了解指令、洞察和 AI 工作台背后的设计原则，请阅读[产品设计](product-design.md)。

For annotated screenshots and step-by-step entry points, see [UI Guide / 带图界面指引](ui-guide.md).

如需查看带标注截图和分步入口说明，请阅读[界面指引](ui-guide.md)。

## Current feature surfaces / 当前功能面

| Surface / 功能面 | Evidence in project / 项目依据 | User value / 用户价值 |
|---|---|---|
| AI助手 / Office AI Ribbon | word.xml, excel.xml, ppt.xml, installer messages | Start commands, suggestions, search, settings, feedback |
| 指令工厂 / Command editor | Ribbon callbacks and command editor UI | Turn repeated steps into reusable commands |
| 工具箱 / Toolbar and script library | ScriptRegistry and command catalog | Keep trusted commands one click away |
| AI工作台 / Assistant workbench | Installer and UI surfaces | Preview, apply, and rollback assistant actions |
| Workflow Host | Host dispatcher, orchestration, and Host API | Execute bounded local plans and VBS functions |
| Preview and rollback | Preview actions, write plans, history manager | Review changes before writing documents |
| Feedback and diagnostics | VbsProxy telemetry/feedback paths | Submit selected diagnostics for support |

Feature availability can vary by Release, Office application, user settings, and account/network state. Release notes are authoritative for a specific build.

具体功能可能因 Release、Office 应用、用户设置、账号和网络状态变化，以对应 Release 说明为准。

## Low-disruption design / 低打扰设计

The engineering target is low resident overhead and minimal interruption to Office work:

- local Office operations are preferred for local tasks;
- read-only context and preview steps are separated from write steps;
- write operations should expose a plan, confirmation, backup, and rollback path;
- long or batch operations should have budget and failure reporting;
- AI and network actions are user-triggered or controlled by the active settings.

工程目标是低常驻开销和尽量少打扰 Office 工作：本地任务优先使用本地能力；只读上下文、预览和写入分开；写入操作提供计划、确认、备份和回滚；长任务提供预算和失败报告；AI/网络行为受用户操作和当前设置控制。

No public numeric CPU, memory, IO, or hardware guarantee is made yet. See performance.md.

## Product boundary / 产品边界

The product includes proprietary client binaries, installer logic, backend services, and online features. Community VBS, prompts, schemas, and examples are maintained separately in lonardo/clippad_functions under Apache-2.0.

产品包括专有客户端二进制、安装逻辑、后端服务和在线功能；公共 VBS、提示词、Schema 和示例在 lonardo/clippad_functions 中按 Apache-2.0 管理。
