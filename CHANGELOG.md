# Changelog / 更新日志

All public product changes must be copied from the matching signed Release. This file must not contain a version or date that has not actually been published.

所有公开产品变更必须从对应的签名 Release 同步。本文件不得填写尚未真实发布的版本号或日期。

## Unreleased / 未发布

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
