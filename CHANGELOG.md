# Changelog / 更新日志

All public product changes must be copied from the matching signed Release. This file must not contain a version or date that has not actually been published.

所有公开产品变更必须从对应的签名 Release 同步。本文件不得填写尚未真实发布的版本号或日期。

## [1.0.0.1011] - 2026-09-03\n\n### Fixed / 修复\n- Fixed Excel AI workbench selection reading and applying generated content to the selected cells.\n- Fixed keyboard routing in the AI workbench and global search window, including English, numbers, punctuation, editing, and navigation keys.\n- Fixed Excel global search mode persistence and Ribbon visibility synchronization.\n- Improved queued/concurrent AI workbench sessions, cancellation, timeout recovery, localized layout, and docking stability.\n- Added lifecycle telemetry deduplication and protected the VbsWorker during add-in shutdown.\n\n### Compatibility / 兼容性\n- Windows Office COM add-in for Word, Excel, and PowerPoint; production package includes signed x86/x64 components.\n- Staging validation completed before production publication.\n\n### Security / 安全\n- No new third-party promotion or bundled software. Production payment test mode remains disabled.\n\n## Unreleased / 未发布

### Documentation / 文档

- Expanded bilingual installation, usage, compatibility, privacy, security, support, and release guidance.
- Added an explicit boundary between the proprietary product repository and the Apache-2.0 community functions repository.
- Documented Office 2010+ compatibility, per-user installation, Host-first VBS usage, and the current no-hardware-number policy.

### Release discipline / 发布纪律

- Every installer Release must include the exact installer filename, four-part version, digital-signature status, SHA256, supported environment, known issues, and rollback notes.
- Product binary versions must be synchronized before release.
- Staging validation must complete before production publication.

## Release entry template / 版本条目模板

When a real Release is published, add an entry in this format:

~~~text
## [X.Y.Z.BUILD] - YYYY-MM-DD

### Added / 新增
- User-visible change.

### Changed / 变更
- User-visible behavior or compatibility change.

### Fixed / 修复
- Reproducible issue fixed.

### Security / 安全
- Security-relevant change or "None".

### Compatibility / 兼容性
- Windows:
- Office:
- Word / Excel / PowerPoint:
- 32/64-bit:

### Assets / 发布资产
- OfficeAddinSetup.exe
- SHA256:
- Signature:
~~~

Do not copy internal implementation plans, customer incidents, private backend details, or legal filing materials into the public changelog.

不要把内部实施计划、客户事件、私有后端细节或申报资料写入公开更新日志。
