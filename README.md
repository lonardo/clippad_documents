# OfficeAddin

OfficeAddin 是面向 Windows 桌面版 Word、Excel 和 PowerPoint 的独立 COM 插件，用于把重复办公操作整理成可复用的命令、工作流和 Host-first VBS 函数。

OfficeAddin is an independent Windows desktop COM add-in for turning repeated Word, Excel, and PowerPoint work into reusable commands, workflows, and Host-first VBS functions.

## Quick links / 快速入口

- Latest Release / 最新版本: https://github.com/lonardo/clippad_documents/releases/latest
- Install / 安装: docs/install.md
- Usage / 使用: docs/usage.md
- Product / 产品介绍: docs/product.md
- Compatibility / 兼容性: docs/compatibility.md
- VBS and Host / VBS 与 Host: docs/vbs.md
- AI VBS generation / AI 生成 VBS: docs/ai-vbs-generation.md
- Open-source boundary / 开源边界: docs/open-source.md
- FAQ: docs/faq.md
- Privacy / 隐私: docs/privacy.md
- Security / 安全: SECURITY.md
- Support / 支持: SUPPORT.md

## Supported scope / 支持范围

- Windows 10/11 desktop / Windows 10/11 桌面版
- Word, Excel, PowerPoint / Word、Excel、PowerPoint
- Office 2010 and newer have been tested / Office 2010 及以上已测试
- No current public claim for Mac, browser-only Office, Windows 7, or Windows 8.1 / 当前不声明支持 Mac、纯 Web Office、Windows 7 或 8.1

## Download / 下载

Download OfficeAddinSetup.exe and the matching SHA256 from the same GitHub Release. The installer is per-user and normally installs to %LOCALAPPDATA%\OfficeAddin.

从同一个 GitHub Release 下载 OfficeAddinSetup.exe 和对应 SHA256。安装程序按当前用户安装，默认目录为 %LOCALAPPDATA%\OfficeAddin。

## Community functions / 公共函数

Public VBS, Host API, prompts, schemas, workflow examples, and contribution tools are maintained separately:

公共 VBS、Host API、提示词、Schema、工作流示例和贡献工具位于独立仓库：

https://github.com/lonardo/clippad_functions

The community repository uses Apache-2.0 for its VBS, examples, prompts, schemas, and original public documentation. The OfficeAddin installer and product binaries remain proprietary.

公共仓库中的 VBS、示例、提示词、Schema 和原创文档采用 Apache-2.0；OfficeAddin 安装包和产品二进制仍按专有产品许可管理。

## Safety / 安全

Review the Release hash and signer before installation. Review VBS source and the preview/confirmation behavior before running commands that write documents or files. Never publish customer files, credentials, private keys, settings.ini, logs, or filing materials in public Issues.

安装前核对 Release 哈希和签名；运行写入文档或文件的命令前检查 VBS 源码和预览/确认行为。不要在公开 Issue 中发布客户文件、凭据、私钥、settings.ini、日志或申报资料。
