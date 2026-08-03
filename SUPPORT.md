# Support / 用户支持

## Before opening an issue / 提交 Issue 前

1. Read docs/install.md for installation or Ribbon problems.
2. Read docs/faq.md for compatibility and usage questions.
3. Confirm the exact Release and installer SHA256.
4. Restart Office once after installation or upgrade.
5. Try a read-only command before a write or AI command.

## Choose the right channel / 选择正确渠道

| Problem / 问题 | Channel / 渠道 |
|---|---|
| Installer, Ribbon, SmartScreen / 安装、功能区、SmartScreen | Install issue template |
| Reproducible product defect / 可复现产品缺陷 | Bug issue template |
| New workflow or feature / 新工作流或功能 | Feature request or Discussion |
| VBS/Host/prompt contribution / VBS、Host、提示词贡献 | lonardo/clippad_functions repository |
| Security vulnerability / 安全漏洞 | Private report to security@clippad.cc |
| Private account or business matter / 私密账号或商业问题 | support@clippad.cc |

## Include this information / 请提供

- OfficeAddin Release version and SHA256;
- Windows version;
- Office application and exact Office version;
- Office architecture: 32-bit, 64-bit, or unknown;
- current document type and whether it is saved;
- selection state and the exact command or VBS name;
- steps to reproduce;
- expected and actual result;
- exact error text;
- a small redacted log fragment if needed.

请提供版本、SHA256、Windows、Office 应用和版本、位数、文档状态、选区状态、脚本名称、复现步骤、期望/实际结果、错误文本和必要的脱敏日志片段。

## Local diagnostic locations / 本地诊断目录

Common locations:

~~~text
%LOCALAPPDATA%\OfficeAddin
%APPDATA%\OfficeAddin\UserProfile
%APPDATA%\OfficeAddin\Logs
%APPDATA%\OfficeAddin\Telemetry
~~~

Do not upload the entire directory. Redact usernames, customer paths, document text, tokens, endpoints, and contact details.

不要上传整个目录；请删除用户名、客户路径、文档文字、令牌、接口、联系方式等信息。

## Do not include / 不要提交

Passwords, tokens, API keys, private documents, customer data, private keys, raw dumps, settings.ini, deployment files, ICP/software-copyright/patent materials, or information that you are not authorized to disclose.

## Contact / 联系方式

- General support: support@clippad.cc
- Security: security@clippad.cc
- Website: https://clippad.cc
