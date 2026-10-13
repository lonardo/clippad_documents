# Changelog / 更新日志

All public product changes must be copied from the matching signed Release. This file must not contain a version or date that has not actually been published.

所有公开产品变更必须从对应的签名 Release 同步。本文件不得填写尚未真实发布的版本号或日期。

## Unreleased / 未发布

Documentation updates that are not tied to a new installer may land here until the next signed Release.

未绑定新安装包的文档更新可先记在这里，直到下一个签名 Release。


## [1.0.0.1014] - 2026-10-13

### Fixed / 修复

- Fixed the problem where clicking the font checkbox opened the global search dropdown.
- 修复点击字体复选框弹出全局搜索下拉窗口的问题。
- Fixed confirmed Excel insight recommendations not appearing after repeated edits.
- 修复 Excel 重复编辑后，已确认的洞察推荐不出现的问题。
- Fixed bound Excel recommendations failing to appear when they have no text box.
- 修复 Excel 已绑定推荐因为没有输入框而弹不出来的问题。
- Fixed bound commands going silent when the generic corner-recommendation switch is turned off. Dismissing one command does not mute the others.
- 修复关闭“主动弹出右下角推荐”后，已绑定指令也不再提醒的问题，关掉一条不会把其他指令一起静音。
- Fixed confirmed bindings being skipped when the match was not strong enough. Repeat count and cooldown still apply.
- 修复已确认的洞察绑定因为匹配不够而不出推荐的问题，重复次数和冷却仍然有效。
- Fixed recommendations that kept appearing after a binding was removed. Search and the toolbar can still run the command.
- 修复删除洞察绑定后仍然继续推荐的问题，搜索和工具栏仍可手动运行。
- Fixed Word, Excel, or PowerPoint hanging on close, and no longer quitting PowerPoint that is still in use.
- 修复关闭 Word、Excel 或 PowerPoint 时卡住的问题，也不会误退出正在使用的 PowerPoint。
- Fixed PowerPoint showing insight recommendations.
- 修复 PowerPoint 误显示洞察推荐的问题。
- Fixed preview of an existing workbench command doing nothing. Repeated clicks are combined into one preview.
- 修复工作台里已有指令点预演没有反应的问题，重复点击会合并成一次。
- Fixed a failed insight refinement being written into the script body.
- 修复细化洞察建议失败后，异常文字被写进脚本正文的问题。
- Fixed binding review and recommendation buttons that were missing English.
- 修复绑定审阅和推荐按钮缺少英文的问题。
- Fixed isolated Excel preview changing the workbook's original format.
- 修复 Excel 隔离预演改变工作簿原格式的问题。

### Improved / 优化

- Improved the first click of a preview-first command: it opens only the local plan, and the document changes after confirm. Cancel or failure does not run the script.
- 优化先预演指令的第一次点击：只打开本地计划，确认后才改文档，取消或失败不会运行脚本。

### Added / 新增

- Added local insight binding for Word and Excel. A confirmed declaration is written in the script header, and the index sits beside the script folder. The model cannot write a confirmed binding. Unconfirmed suggestions stay in review. Automatic confirmation is rejected.
- 新增 Word 和 Excel 的本地洞察绑定，确认后写在脚本头部，索引放在脚本目录旁边。模型不能自行写入已确认绑定，未确认建议只留在审阅里，自动确认会被拒绝。

### Extended / 拓展

- Extended the Excel Host methods shown while writing scripts. Only implemented methods are shown.
- 拓展写脚本时可见的 Excel Host 方法，只展示已经实现的方法。


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
- SHA256: published with the signed Release
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
