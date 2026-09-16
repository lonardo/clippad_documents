# OfficeAddin for Word, Excel, and PowerPoint

OfficeAddin is a Windows desktop Office add-in for turning repeated Word, Excel, and PowerPoint work into reusable commands, workflows, and Host-first VBS functions.

OfficeAddin 是面向 Windows 桌面版 Word、Excel 和 PowerPoint 的插件，用于把重复办公操作整理成可复用的命令、工作流和 Host-first VBS 函数。

[Latest release / 最新版本](https://github.com/lonardo/clippad_documents/releases/latest) · [Product / 产品](docs/product.md) · [Product design / 产品设计](docs/product-design.md) · [Try it / 试用场景](docs/try-it.md) · [Install / 安装](docs/install.md) · [Usage / 使用](docs/usage.md) · [UI guide / 带图界面指引](docs/ui-guide.md) · [VBS / Host](docs/vbs.md) · [AI VBS generation / AI 生成 VBS](docs/ai-vbs-generation.md) · [Open source / 开源](docs/open-source.md) · [FAQ](docs/faq.md) · [Privacy / 隐私](docs/privacy.md) · [Security / 安全](SECURITY.md)

## What it does / 产品定位

OfficeAddin places local Office automation inside the Office Ribbon. It supports reusable commands, a command editor, workflow execution, a script library, preview-oriented operations, and optional AI-assisted actions.

OfficeAddin 把本地 Office 自动化能力放在 Office 功能区中，提供可复用命令、指令工厂、工作流执行、脚本库、面向预览的操作以及可选的 AI 辅助功能。

### Word

- selection and document cleanup / 选区和文档清理
- formatting and delivery checks / 排版和交付前检查
- outline, review, comments, and revision workflows / 大纲、审阅、批注和修订流程
- reusable local VBS commands / 可复用本地 VBS 命令

### Excel

- selection and range cleanup / 选区和区域清洗
- formula and data-quality checks / 公式和数据质量检查
- summaries, field mapping, deduplication, and export / 汇总、字段映射、去重和导出
- preview-first worksheet operations / 以预览为前置的工作表操作

### PowerPoint

- text, title, footer, and page-number workflows / 文本、标题、页脚和页码流程
- layout and object checks / 版式和对象检查
- outline, notes, and slide asset export / 大纲、备注和幻灯片资源导出
- reusable presentation cleanup commands / 可复用演示文稿清理命令

### Command, workflow, and AI features / 命令、工作流和 AI

- turn repeated manual work into one-click commands / 把重复手工流程变成一键命令
- preview, confirm, backup, commit, and rollback for write operations / 写入操作支持预览、确认、备份、提交和回滚
- use Host API instead of unsafe ad-hoc script COM helpers / 优先使用 Host API，而不是脚本中自行创建不受控 COM 辅助对象
- AI features are optional and are triggered by the user / AI 功能是可选的，由用户主动触发

## Compatibility / 兼容性

- Windows XP and newer desktop / Windows XP 及以上桌面版
- Microsoft Word, Excel, and PowerPoint / Microsoft Word、Excel 和 PowerPoint
- Office 2010 and newer have been tested / Office 2010 及以上版本已测试
- 32-bit and 64-bit behavior must be reported with each issue / 提交问题时请说明 32 位或 64 位
- Mac and browser-only Office are not part of the current public support claim / 当前不声明支持 Mac 或纯 Web Office

No hardware minimum is published yet. We will publish measured resource data only with a reproducible release test matrix.

当前暂不发布硬件最低参数。CPU、内存和 IO 数据只有在形成可复现的 Release 测试矩阵后才会公开。

## Download and install / 下载与安装

Download OfficeAddinSetup.exe and its SHA256 value from the matching GitHub Release. The installer is per-user and normally installs under %LOCALAPPDATA%\OfficeAddin; administrator permission is not the default requirement.

从对应 GitHub Release 下载 OfficeAddinSetup.exe 及 SHA256 校验值。安装程序默认按当前用户安装到 %LOCALAPPDATA%\OfficeAddin，通常不要求管理员权限。

Before installing:

1. Save important Office work.
2. Close Word, Excel, and PowerPoint.
3. Verify the digital signature and SHA256.
4. Run the installer.
5. Reopen Office and look for the Office AI / AI助手 Ribbon tab.

安装前请保存重要文档、关闭 Office、核对数字签名和 SHA256；安装完成后重新打开 Office，在 Office AI / AI助手功能区中开始使用。

## Community functions / 公共创作仓库

The reusable VBS and prompt materials are published separately:

https://github.com/lonardo/clippad_functions

It contains Host-first VBS functions, host/host-api-v1.json, workflow and schema examples, prompts for generation and repair, and contribution/testing guidance.

VBS, examples, prompts, schemas, and original community documentation in that repository are released under Apache-2.0 unless a file says otherwise.

可复用 VBS、Host API、Schema、提示词和原创公共文档位于独立仓库，并采用 Apache-2.0；产品 DLL、安装包和在线服务仍按产品许可管理。

## Data and safety / 数据与安全

Local commands operate on the active Office context and user-selected local files. AI, feedback, update, telemetry, or diagnostic features may use network services according to the exact build and settings. Review docs/privacy.md before processing confidential documents.

本地命令处理当前 Office 上下文和用户指定的本地文件。AI、反馈、更新、遥测或诊断功能可能按具体版本和设置使用网络服务。处理敏感文档前请阅读隐私说明。

Never upload passwords, tokens, private documents, customer data, private keys, or unredacted logs to public Issues.

请勿在公开 Issue 中上传密码、令牌、私有文档、客户数据、私钥或未脱敏日志。

## Support / 支持

- Installation and ribbon issues: docs/install.md and the Install issue template / 安装问题请先阅读安装指南并使用安装 Issue 模板。
- Reproducible product bugs: the bug report template / 可复现缺陷请使用 Bug 模板。
- Workflow ideas: the feature request template / 工作流想法请使用功能请求模板。
- Security problems: follow SECURITY.md and report privately / 安全问题请按 SECURITY.md 私密报告。

## License boundary / 许可证边界

The published installer and product binaries are proprietary. See LICENSE. The Apache-2.0 community code is maintained in lonardo/clippad_functions; do not infer an open-source license for the installer from that repository.

公开安装包和产品二进制仍是专有软件，详见 LICENSE。Apache-2.0 公共代码位于 lonardo/clippad_functions，不能据此推断安装包也属于开源软件。
