# Installation Guide / 安装指南

This guide describes the current OfficeAddin installer behavior derived from setup/OfficeAddin.iss. Release-specific notes and hashes always take precedence over this general guide.

本文档依据 setup/OfficeAddin.iss 的当前实现整理。具体 Release 的安装说明、签名和 SHA256 优先于本文档的一般说明。

## Supported environment / 支持环境

- Windows 10 or Windows 11 desktop / Windows 10 或 Windows 11 桌面版
- Word, Excel, and/or PowerPoint / Word、Excel 和/或 PowerPoint
- Office 2010 and newer have been tested / Office 2010 及以上已测试
- The current public claim does not include Mac, browser-only Office, Windows 7, or Windows 8.1 / 当前不声明支持 Mac、纯 Web Office、Windows 7 或 Windows 8.1

The installer is per-user. Its default installation directory is:

安装程序按当前用户安装，默认目录为：

~~~text
%LOCALAPPDATA%\OfficeAddin
~~~

The installer script sets PrivilegesRequired=lowest. Do not ask users to run it as administrator unless a specific enterprise policy or error diagnosis requires that step.

安装脚本设置了 PrivilegesRequired=lowest。除非企业策略或具体错误诊断明确要求，否则不要让用户以管理员身份运行。

## Before installing / 安装前

1. Save important documents and close Word, Excel, and PowerPoint.
2. Download OfficeAddinSetup.exe only from the matching GitHub Release or official website.
3. Confirm that the download filename, Release version, SHA256, and signer match.
4. Keep the Release notes available in case the build has a known upgrade action.

1. 保存重要文档并关闭 Word、Excel、PowerPoint。
2. 只从对应 GitHub Release 或官网下载安装包。
3. 核对文件名、Release 版本、SHA256 和数字签名。
4. 阅读该版本的已知问题和升级说明。

## Verify the installer / 验证安装包

PowerShell SHA256 check:

~~~powershell
Get-FileHash .\OfficeAddinSetup.exe -Algorithm SHA256
~~~

PowerShell signature check:

~~~powershell
Get-AuthenticodeSignature .\OfficeAddinSetup.exe | Format-List Status,SignerCertificate,StatusMessage
~~~

The expected signer name and hash must come from the same GitHub Release. A valid hash without a trusted download source is not enough.

期望的签名者名称和 SHA256 必须来自同一个 GitHub Release。只有哈希值、没有可信下载来源并不能证明安装包可信。

## Standard install / 标准安装

1. Run OfficeAddinSetup.exe.
2. Read and accept both the User Agreement and Privacy Policy shown by the installer.
3. Keep the detected language unless you need to switch between English and Simplified Chinese.
4. Complete the per-user installation.
5. Reopen Word, Excel, or PowerPoint.
6. Look for the Office AI / AI助手 Ribbon tab.

安装程序会按当前用户注册 Word、Excel 和 PowerPoint 的 COM Add-in。它也会准备用户配置、日志、遥测和脚本命令目录；这些目录属于运行数据，不应上传到公开仓库或 Issue。

## First-run smoke check / 首次运行检查

Run checks in this order:

1. Confirm the Ribbon tab is visible.
2. Open the settings page and confirm the UI language is readable.
3. Run a read-only command or context diagnostic.
4. Run a small local workflow on a disposable document.
5. Only then try AI, batch processing, feedback, or document-writing actions.

建议依次检查：功能区、设置页、只读命令、可丢弃文档上的小型工作流，然后再使用 AI、批处理、反馈和写入文档功能。

## If the Ribbon is missing / 找不到功能区

1. Close every Word, Excel, and PowerPoint window.
2. Start one Office application again.
3. Open File > Options > Add-ins.
4. At the bottom, choose COM Add-ins and select Go.
5. Confirm that OfficeAddin is enabled.
6. Check Disabled Items and re-enable OfficeAddin if listed.
7. Restart Office again.
8. If the issue remains, reinstall the same signed Release or open an Install issue.

如果仍找不到功能区，请记录 Office 应用、Office 版本、Windows 版本、32/64 位、安装包版本和是否被杀毒软件隔离，再提交安装 Issue。

## SmartScreen and antivirus / SmartScreen 与杀毒软件

New or infrequently downloaded installers may receive reputation warnings. Do not bypass a warning blindly.

新发布或下载量较少的安装包可能触发信誉提示，不要盲目绕过警告。

- Check the digital signer.
- Compare the SHA256 with the Release body.
- Download again from the official Release if the hash differs.
- Ask enterprise IT to approve the signer or exact hash when application control blocks the installer.
- Do not accept a community mirror as an official source.

## Upgrade / 升级

1. Read the Release notes for behavior changes.
2. Close Office before starting the upgrade.
3. Prefer installing the newer signed build over the existing per-user installation.
4. Reopen Office and run the first-run smoke check.
5. If the Ribbon or command index is stale, restart Office once more.
6. Keep the old installer and hash until the new build is verified.

正式 Release 必须同步更新四段版本号、安装包、客户端资源和升级清单。升级清单的版本、包地址和哈希必须与 Release asset 对应。

## Uninstall / 卸载

1. Close Word, Excel, and PowerPoint.
2. Open Windows Settings > Apps > Installed apps.
3. Select OfficeAddin / 智能办公插件 and choose Uninstall.
4. Reopen Office and confirm that the Ribbon entry is gone.

The installer owns the per-user registration and the application directory. User data may remain under the OfficeAddin user profile, Logs, or Telemetry directories according to the current product cleanup policy; preserve needed diagnostics before deletion.

## Logs and support data / 日志与支持资料

Common user-data locations are:

~~~text
%LOCALAPPDATA%\OfficeAddin
%APPDATA%\OfficeAddin\UserProfile
%APPDATA%\OfficeAddin\Logs
%APPDATA%\OfficeAddin\Telemetry
~~~

Attach only the smallest redacted log fragment needed for diagnosis. Do not upload settings.ini, tokens, full documents, private paths, or crash dumps containing sensitive data.

## Silent or managed deployment / 静默或企业部署

Interactive installation is the public documented path. Silent arguments are Release-specific and must be tested with the exact installer before being documented for enterprise use. Do not invent MSI-style parameters for this Inno Setup package.

## Still stuck? / 仍然无法安装

Use the Install / ribbon missing issue template and include the exact error text, version, Office app, Windows version, architecture, download source, and steps already tried.
