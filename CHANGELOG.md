# Changelog / 更新日志

All public product changes must be copied from the matching signed Release. This file must not contain a version or date that has not actually been published.

所有公开产品变更必须从对应的签名 Release 同步。本文件不得填写尚未真实发布的版本号或日期。

## Unreleased / 未发布

Documentation updates that are not tied to a new installer may land here until the next signed Release.

未绑定新安装包的文档更新可先记在这里，直到下一个签名 Release。

## [1.0.0.1013] - 2026-09-29

### Added / 新增

- None.

### Changed / 变更

- Opening an insight in the AI workbench carries the observed selection and operation into the task.
- Excel cross-sheet confirmation uses one frameless prompt.

### Fixed / 修复

- Workbench typing in Word and Excel keeps Chinese input, paste, shortcuts, and returned focus in the workbench.
- Preview confirmation stays above the preview.
- Reopening the workbench restores the locally saved preview and task note when that record exists.
- A blank workbench page attempts to recover instead of staying empty.

### Security / 安全

- None.

### Compatibility / 兼容性

- Windows: desktop Windows with Office 2010 or later, including Microsoft 365 desktop.
- Office: Word, Excel, PowerPoint.
- 32/64-bit: both, matching the installed Office bitness.

### Assets / 发布资产

- OfficeAddinSetup.exe
- SHA256: f5715ae301e03305036d8fca1a5f026b262f74481c06e179e621a5171529165a
- Signature: Valid (Ningbo Wang)

Public GitHub Release: https://github.com/lonardo/clippad_documents/releases/tag/1.0.0.1013

## [1.0.0.1012] - 2026-09-16

### Added / 新增

- None. This build tightens existing insight, Excel candidate, and startup/close behavior.

### Changed / 变更

- Visible insight prompts require repeated independent behavior in the same document.
- Excel cross-sheet reconciliation cards appear only when workbook, sheet, and selection context is stable.
- Excel avoids UIA tracking before a workbook is opened.

### Fixed / 修复

- Word/Excel insight trigger boundaries and Excel start-page close interaction with UIA.
- Suggestion card layout and action affordances.

### Security / 安全

- None.

### Compatibility / 兼容性

- Windows: desktop Windows with Office 2010 or later, including Microsoft 365 desktop.
- Office: Word, Excel, PowerPoint.
- 32/64-bit: both, matching the installed Office bitness.

### Assets / 发布资产

- OfficeAddinSetup.exe
- SHA256: 5d6bfb7c143f60ed28cddbf3edd2e3b5e31053d755e19a3a2e30fd2754bad0af
- Signature: Valid (Ningbo Wang)

Public GitHub Release: https://github.com/lonardo/clippad_documents/releases/tag/1.0.0.1012

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
