# Release Process / 发布流程

This is the public-safe release description. Credentials, private server names, private paths, and deployment commands belong in the private operations runbook.

本文档只描述可公开的发布流程。凭据、私有服务器名称、私有路径和部署命令必须留在私有运维手册中。

## Repositories / 仓库

- Product documents and installer Release: lonardo/clippad_documents
- Community functions and Host materials: lonardo/clippad_functions

## Version source of truth / 版本事实源

For a formal client Release, the four-part version must agree across:

- setup/OfficeAddin.iss AppVersion;
- Plugin/OfficePluginAI.rc;
- VbsProxy/VbsProxy.rc;
- VbsWorker/VbsWorker.rc;
- installer output and Release title;
- upgrade manifest and release evidence.

Run the repository version-sync process before compiling Release binaries. Do not create a Release from a source tree where installer and binary resource versions differ.

## Staging-first flow / 先 staging

1. Review the change list and public boundary.
2. Run code, VBS, documentation, encoding, and license checks.
3. Synchronize the four-part version.
4. Build unsigned or signed staging artifacts according to the release checklist.
5. Verify install, upgrade, uninstall, Ribbon, Word, Excel, PowerPoint, VBS, preview, rollback, and online-feature behavior.
6. Publish or upload staging evidence.
7. Ask for explicit production confirmation.
8. Only after confirmation, publish the production Release/manifest.

## Release assets / Release 资产

Each product Release should contain:

- OfficeAddinSetup.exe;
- SHA256;
- valid Authenticode signature information;
- bilingual change summary;
- supported Windows/Office matrix;
- known issues and rollback notes;
- privacy/network behavior changes;
- compatible community functions tag/commit.

## Community functions release / 公共函数发布

Each public functions Release should contain:

- VBS and examples ZIP;
- Host API JSON;
- prompt and schema versions;
- SHA256;
- Apache-2.0 LICENSE and NOTICE;
- public validation output;
- changed script list and risk classification.

## GitHub synchronization / GitHub 同步

The workstation pushes reviewed commits to the approved internal Git service. An authenticated server-side process then synchronizes the two GitHub repositories and creates Releases. Tokens and private keys must never appear in remotes, scripts, logs, commits, or public documentation.

工作站将审查后的提交推送到批准的内部 Git 服务，再由已认证的服务器侧流程同步两个 GitHub 仓库并创建 Release。Token 和私钥不得出现在 remote、脚本、日志、提交或公开文档中。

## Rollback / 回滚

If a staging package, raw file, website link, hash, or Release asset fails validation, stop publication and revert the staging publication through the approved server process. Do not manually half-switch public routes or upgrade manifests.

如果 staging 包、raw 文件、网站链接、哈希或 Release 资产验证失败，应停止发布并通过批准的服务器流程回滚 staging，不要手动半切换公共路由或升级清单。
