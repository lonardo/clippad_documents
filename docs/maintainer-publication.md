# Maintainer Publication Notes / 维护者发布说明

This page is for maintainers preparing the two public repositories. It may remain in the source staging directory and should be reviewed before copying the directory to GitHub.

本文档供维护者准备两个公共仓库使用。将目录复制到 GitHub 前应再次审核是否需要保留本页。

## Repository mapping / 仓库映射

- github/ -> https://github.com/lonardo/clippad_documents
- open_source/ -> https://github.com/lonardo/clippad_functions

The public documents repository contains product documentation and signed Release assets. The public functions repository contains Apache-2.0 community materials. Do not push the parent engineering repository as either public repository.

## Current source audit / 当前源文件审计

As of 2026-08-08, setup/OfficeAddin.iss still defaults to 1.0.0.1004, while Plugin/OfficePluginAI.rc, VbsProxy/VbsProxy.rc, VbsWorker/VbsWorker.rc, and scripts/build_installer.ps1 already reference 1.0.0.1006. This remains a formal product Release blocker, not a public version claim. Community pack scripts and product installer versions are separate artifacts.

Before a formal product Release:

1. choose the final four-part version;
2. run scripts/sync_client_version.ps1;
3. build Release binaries;
4. verify FileVersion and ProductVersion for every packaged binary;
5. verify setup AppVersion;
6. build the installer;
7. calculate SHA256 after final signing;
8. update CHANGELOG and Release body from the final assets.

## Public allowlist / 公共白名单

For clippad_documents:

- README.md;
- docs/;
- SECURITY.md;
- SUPPORT.md;
- LICENSE;
- CHANGELOG.md;
- RELEASE_TEMPLATE.md;
- .github/ISSUE_TEMPLATE/.

For clippad_functions:

- the reviewed open_source/ directory;
- no parent-repository files outside the reviewed export.

## Exclusions / 排除项

Never export copyright_submission, icp_filing, patent, patent_submission, app_market_submission, backend, logs, dist, private environment files, signing keys, private certificates, customer data, or private operational notes.

永远不要导出软著、ICP备案、专利、市场申报、后端、日志、dist、本地环境文件、签名私钥、私有证书、客户数据或私有运维说明。

## Staging checklist / staging 检查

- [ ] Documentation links resolve.
- [ ] README links to the correct community repository.
- [ ] Raw host-api-v1.json is reachable from clippad_functions.
- [ ] VBS and prompt versions are identified.
- [ ] Installer version and binary resource versions match.
- [ ] Staging install, upgrade, uninstall, Ribbon, Word, Excel, PowerPoint, VBS, preview, and rollback checks pass.
- [ ] Release asset SHA256 and Authenticode signature are verified.
- [ ] No production URL or upgrade manifest is changed without explicit confirmation.

## Git and GitHub workflow / Git 与 GitHub 流程

The workstation commits only the reviewed files and pushes to the approved internal Git service. An authenticated server-side process synchronizes GitHub. GitHub tokens and private keys stay on the server and never enter the repository.

工作站只提交审查后的文件并推送到批准的内部 Git 服务；已认证的服务器侧流程负责同步 GitHub。GitHub Token 和私钥只保留在服务器，不进入仓库。

Do not put private server names, filesystem paths, credentials, or deployment commands in a public README.
