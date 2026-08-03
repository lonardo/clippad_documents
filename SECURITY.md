# Security Policy / 安全政策

## Supported versions / 支持版本

Security fixes target the latest signed GitHub Release. Older builds are best effort only and may not receive fixes.

安全修复以最新签名 GitHub Release 为目标。旧版本仅尽力维护，不保证持续修复。

| Version / 版本 | Support / 支持 |
|---|---|
| Latest signed Release / 最新签名版本 | Yes / 是 |
| Older releases / 较旧版本 | Best effort / 尽力而为 |
| Unofficial mirrors / 非官方镜像 | No / 不支持 |

## Product security expectations / 产品安全要求

- Download installers only from the official GitHub Release or official website.
- Verify the Authenticode signer and SHA256 from the matching Release.
- Treat VBS as executable code: review source, Host permissions, input paths, output paths, and write behavior before running.
- Prefer Host-first functions, preview, confirmation, backup, and rollback.
- Keep Office, Windows, and endpoint protection updated.

- 只从官方 GitHub Release 或官网下载安装包。
- 使用同一 Release 的数字签名和 SHA256 校验。
- 把 VBS 当作可执行代码审查，运行前检查 Host 权限、输入路径、输出路径和写入行为。
- 优先使用 Host-first 函数、预览、确认、备份和回滚。
- 保持 Office、Windows 和终端防护软件更新。

## Report privately / 私密报告

Report suspected vulnerabilities privately to:

安全漏洞请私密发送至：

~~~text
security@clippad.cc
~~~

If this address is unavailable, do not publish exploit details in a public Issue; contact the maintainers through the official website or GitHub private reporting capability.

如果该邮箱暂时不可用，不要在公开 Issue 中发布利用细节，请通过官网或 GitHub 私密报告能力联系维护者。

Include:

- affected Release or commit;
- Windows and Office versions, including 32/64-bit;
- impact and attack preconditions;
- minimal reproduction or proof of concept;
- whether the report contains customer or personal data.

请提供受影响的 Release/提交、Windows 和 Office 版本及位数、影响和攻击前提、最小复现方式，以及报告是否含客户或个人数据。

## Do not publish / 不要公开

- private documents or customer data;
- passwords, API keys, tokens, certificates, or private keys;
- unredacted settings.ini, telemetry outboxes, logs, or dumps;
- arbitrary file write/delete or Office document corruption details before triage;
- unpublished signing, deployment, ICP, software-copyright, patent, or market-submission materials.

## Disclosure / 披露

Maintainers will assess impact, reproduce on a supported staging build, prepare a fix, and publish a coordinated advisory when appropriate. Do not assume that a public issue is a security report.

维护者会评估影响，在支持的 staging 构建上复现并准备修复，必要时协同发布安全公告。公开 Issue 不等同于安全报告。
