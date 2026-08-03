# OfficeAddin X.Y.Z.BUILD

简体中文和 English 的 Release 说明必须描述同一组真实资产。所有字段在发布前填写，不用虚构值。

## Highlights / 重点

### 中文

-

### English

-

## Supported environment / 支持环境

- Windows 10 / Windows 11 desktop
- Office 2010 and newer, as tested for this Release
- Word / Excel / PowerPoint:
- Office architecture:
- Exact tested Office builds:

## Downloads / 下载

- File: OfficeAddinSetup.exe
- Size:
- SHA256:
- Authenticode signer:
- Signature status:

Verify on Windows:

~~~powershell
Get-FileHash .\OfficeAddinSetup.exe -Algorithm SHA256
Get-AuthenticodeSignature .\OfficeAddinSetup.exe | Format-List Status,SignerCertificate,StatusMessage
~~~

## Installation / 安装

1. Close Word, Excel, and PowerPoint.
2. Verify the matching Release hash and signer.
3. Run OfficeAddinSetup.exe.
4. Reopen Office and check Office AI / AI助手.
5. Run a read-only smoke check before a write or AI action.

## Changes / 变更

### Added / 新增

-

### Changed / 变更

-

### Fixed / 修复

-

### Security / 安全

-

## VBS and community functions / VBS 与公共函数

- Community functions release:
- Host API version:
- Prompt pack version:
- Public functions SHA256, if attached:
- Any incompatible Host API or script changes:

Community code is maintained at https://github.com/lonardo/clippad_functions and does not change the proprietary license of the installer.

## Known issues / 已知问题

-

## Privacy and network / 隐私与网络

State whether this Release changes AI, feedback, update, telemetry, crash, account, or VBS-market behavior. Do not put tokens, private endpoints, or internal server configuration in the Release body.

说明本版本是否改变 AI、反馈、更新、遥测、崩溃、账号或 VBS 市场行为。不要在 Release 正文中放置令牌、私有接口或内部服务器配置。

## Verification evidence / 验证证据

- [ ] Version resources and installer AppVersion are synchronized.
- [ ] Staging build completed.
- [ ] Install, upgrade, uninstall, and Ribbon smoke completed.
- [ ] Word smoke completed.
- [ ] Excel smoke completed.
- [ ] PowerPoint smoke completed.
- [ ] VBS/Host validation completed.
- [ ] Public documentation and raw community files point to this version.
- [ ] SHA256 and signature checked after final packaging.
- [ ] Production publication has explicit approval.

## Support / 支持

- Issues: use the GitHub templates.
- General: support@clippad.cc
- Security: security@clippad.cc
