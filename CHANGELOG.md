# Changelog / 更新日志

All public product changes must be copied from the matching signed Release. This file must not contain a version or date that has not actually been published.

所有公开产品变更必须从对应的签名 Release 同步。本文件不得填写尚未真实发布的版本号或日期。

## Unreleased / 未发布

Documentation updates that are not tied to a new installer may land here until the next signed Release.

未绑定新安装包的文档更新可先记在这里，直到下一个签名 Release。


## [1.0.0.1014] - 2026-10-13

### Added / 新增

- Word and Excel can confirm a local insight trigger. The confirmed declaration lives in the script header, and the index lives beside the script folder.
- Word 和 Excel 可为本机指令确认洞察触发。确认后的声明写在脚本头部，索引放在脚本目录旁边。

### Changed / 变更

- This even build is a stability release. Install and upgrade behavior is unchanged.
- A preview-first command opens only the local plan on the first click and changes the document after confirm.
- Registered Excel Host methods are shown to script authors. Methods that are not implemented are not presented as callable.
- 这是偶数稳定版。安装和升级方式不变。
- 先预演的指令第一次点击只打开本地计划，确认后才改文档。
- 写脚本时可以看到已登记的 Excel Host 方法。没有实现的方法不会被写成可调用接口。

### Fixed / 修复

- A confirmed Excel insight binding recommends after repeated edits and is no longer dropped by the score gate. Repeat count and cooldown still apply.
- A bound Excel recommendation appears even when it has no text box, and it does not follow the generic corner-popup switch. Dismissing one command does not mute the others.
- Removing a binding stops recommendations. Search and the toolbar can still run it.
- Closing Word, Excel, or PowerPoint no longer hangs and does not quit the user's PowerPoint. PowerPoint does not show insight recommendations.
- Binding review and recommendation buttons are available in Chinese and English.
- Existing-command preview callbacks are connected, and repeated preview attempts are coalesced.
- Refining an insight suggestion no longer carries a failure into the script body.
- Ribbon dropdowns no longer take global search focus.
- Isolated Excel preview keeps the workbook's original format.
- The model cannot write a confirmed binding. An unconfirmed suggestion stays in review. Automatic confirmation is rejected.
- Excel 已确认的洞察绑定会在重复编辑后弹出推荐，不再被评分门槛拦住。重复次数和冷却仍然有效。
- Excel 已绑定推荐不再因没有输入框而弹不出，也不跟随“主动弹出右下角推荐”。关闭一条不会静音其他指令。
- 删除绑定后推荐停止。搜索和工具栏仍可手动运行。
- 关闭 Word、Excel、PowerPoint 不再卡住，也不会退出正在使用的 PowerPoint。PowerPoint 不显示洞察推荐。
- 绑定审阅和推荐按钮提供中英文。
- 工作台已有指令的预演回调已接上，重复预演会合并。
- 细化洞察建议时不再把异常带进脚本正文。
- 功能区下拉框不再抢走搜索焦点。
- Excel 隔离预演保留工作簿原格式。
- 模型不能自行写入已确认绑定。未确认建议只留在审阅中。自动确认会被拒绝。

### Security / 安全

- None.

### Compatibility / 兼容性

- Windows: desktop Windows with Office 2010 or later, including Microsoft 365 desktop.
- Office: Word, Excel, PowerPoint.
- 32/64-bit: both, matching the installed Office bitness.
- PowerPoint does not show insight recommendations in this build.

### Assets / 发布资产

- OfficeAddinSetup.exe
- SHA256: 2eaf84bd93ab651df2300d14b9fb1379e2fbce4b4509987ce1d46f9eb573d6b3
- Signature: Valid (Ningbo Wang)

Public GitHub Release: https://github.com/lonardo/clippad_documents/releases/tag/1.0.0.1014

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
