# FAQ / 常见问题

## Product / 产品

### What is OfficeAddin? / OfficeAddin 是什么？

OfficeAddin is an independent Windows desktop COM add-in for Word, Excel, and PowerPoint. It provides commands, workflows, a script library, preview-oriented actions, and optional AI assistance.

OfficeAddin 是独立的 Windows 桌面 COM 插件，集成 Word、Excel 和 PowerPoint，提供命令、工作流、脚本库、预览型操作和可选的 AI 辅助。

### Is it a Microsoft product? / 是微软官方产品吗？

No. OfficeAddin is an independent product that integrates with Microsoft Office. Microsoft, Word, Excel, and PowerPoint are trademarks of their respective owners.

不是。OfficeAddin 是独立产品，集成 Microsoft Office。Microsoft、Word、Excel 和 PowerPoint 归其各自权利人所有。

### Is the entire product open source? / 整个产品都开源吗？

No. The installer, COM DLLs, backend, and online services remain proprietary. Public VBS, prompt, schema, and example materials are maintained separately in lonardo/clippad_functions under Apache-2.0.

不是。安装包、COM DLL、后端和在线服务仍是专有部分；公共 VBS、提示词、Schema 和示例在独立的 lonardo/clippad_functions 仓库中按 Apache-2.0 管理。

## Compatibility / 兼容性

### Which Office versions are supported? / 支持哪些 Office 版本？

Office 2010 and newer have been tested for the current public compatibility claim on Windows desktop. Each Release may have app-specific notes, and an issue should include the exact Office build and 32/64-bit architecture.

当前公开兼容性口径为 Windows 桌面版 Office 2010 及以上。不同 Release 可能有应用专属说明，反馈问题时请提供准确 Office 构建号和 32/64 位架构。

### Does it work on Mac or Office for the web? / 支持 Mac 或 Web 版 Office 吗？

No public support claim is made for Mac or browser-only Office. The product integrates with installed Windows desktop Office applications.

当前不声明支持 Mac 或纯浏览器 Office；产品依赖 Windows 桌面版 Office。

### Is Windows XP or newer supported? / 支持 Windows XP 及以上吗？

Yes. The current public Windows scope is Windows XP and newer desktop versions. Windows 7 has been verified.

支持。当前公开 Windows 范围为 Windows XP 及以上桌面版本，Windows 7 已验证通过。

### What hardware is required? / 最低硬件是什么？

No numeric hardware minimum is published yet. Office version, document size, batch size, and AI workload affect resource usage. Measured CPU, memory, and IO data will be published with a reproducible Release test matrix.

目前不发布未经统一测试的硬件最低数字。资源消耗会受到 Office 版本、文档大小、批量数量和 AI 任务影响；后续只有在形成可复现测试矩阵后才公开数据。

## Install and use / 安装与使用

### Where is it installed? / 安装到哪里？

The current installer is per-user and defaults to %LOCALAPPDATA%\OfficeAddin. User configuration and runtime data are stored under the OfficeAddin folders in LOCALAPPDATA or APPDATA.

当前安装程序按用户安装，默认目录为 %LOCALAPPDATA%\OfficeAddin；用户配置和运行数据位于 LOCALAPPDATA 或 APPDATA 下的 OfficeAddin 目录。

### Why is the Ribbon missing? / 为什么没有功能区？

Close all Office windows, reopen one app, check File > Options > Add-ins > COM Add-ins, and check Disabled Items. If the add-in is enabled but still missing, reinstall the same signed Release and report the exact Office architecture.

关闭所有 Office 窗口后重新打开，检查 COM Add-ins 和 Disabled Items；若仍缺失，请重新安装同一签名 Release 并报告 Office 架构。

### Does installation require administrator permission? / 安装需要管理员权限吗？

The installer is configured for per-user installation and does not require administrator permission by default. Corporate endpoint policy may still block installation.

安装程序默认按当前用户安装，不要求管理员权限；企业终端策略仍可能阻止安装。

### Can local commands work offline? / 本地命令可以离线使用吗？

Local Office operations can work without an AI request or online account. AI, account, update, feedback, telemetry, and online content features may require network access according to the exact build and settings.

未触发 AI 或在线服务时，本地 Office 操作可以离线运行；AI、账号、更新、反馈、遥测和在线内容功能可能需要网络。

## VBS and Host / VBS 与 Host

### Where are public functions? / 公共函数在哪里？

See https://github.com/lonardo/clippad_functions. The repository includes the Host API contract, VBS categories, prompts, examples, schemas, contribution rules, and public validation tool.

### Is Host.GetSelection() usable? / Host.GetSelection() 真正可用吗？

Yes. It is a registered Host method that returns readable text from the current selection without opening a new selection dialog. It is not a Range/Selection COM object. Use Host.GetSelectionInfo() for structured metadata, Host.GetSelectionObject() for object-level operations, and Host.SelectRange() when the user must select a new range.

可以。它是已注册的 Host 方法，读取当前选区可提取的文本，不会再次弹出选择框，也不是 Range/Selection COM 对象。结构化信息使用 Host.GetSelectionInfo()，对象操作使用 Host.GetSelectionObject()，需要用户重新选择时使用 Host.SelectRange()。

### Why can direct cscript execution fail? / 为什么直接 cscript 可能失败？

Public source VBS files use UTF-8 BOM for the add-in loader. Windows cscript has environment-dependent UTF-8 BOM behavior; independent syntax checks should use a temporary UTF-16LE copy. A direct cscript parse failure does not by itself prove the Host script logic is wrong.

公共源 VBS 使用 UTF-8 BOM 供插件加载。Windows cscript 对 UTF-8 BOM 的直接读取存在环境差异；独立语法检查应使用 UTF-16LE 临时副本。直接 cscript 编码失败不等于 Host 脚本逻辑错误。

## Data and accounts / 数据与账号

### Does the add-in upload my whole document? / 会上传整份文档吗？

Local automation uses the active document only for the requested local operation. AI-assisted actions may process selected text, prompts, or required context; feedback and diagnostics may include files or logs that the user explicitly attaches. Read docs/privacy.md for the complete public boundary.

本地自动化只为完成用户请求而读取当前文档；AI 功能可能处理用户选中的文本、提示词和必要上下文；反馈和诊断可能包含用户主动附加的文件或日志。完整边界见 docs/privacy.md。

### Do I need an account? / 需要账号吗？

Some online, community, licensing, or feedback features may require an account. The exact requirement must be stated in the matching Release and website documentation.

部分在线、社区、授权或反馈功能可能需要账号，具体要求以对应 Release 和官网说明为准。

### Is pricing documented here? / 这里有价格说明吗？

No. Commercial terms are maintained outside this repository. Do not infer pricing, free tiers, refunds, or invoice policy from the installer or open-source functions repository.

没有。本仓库不定义商业条款，免费层、退款和发票政策以官网正式说明为准。

## Support / 支持

Use GitHub Issues for reproducible product, installation, and documentation problems. Do not publish security vulnerabilities or private business data.

可复现的产品、安装和文档问题使用 GitHub Issue；安全漏洞和私有业务数据不要公开。
