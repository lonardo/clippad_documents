# Changelog / 更新日志

All public product changes must be copied from the matching signed Release. This file must not contain a version or date that has not actually been published.

所有公开产品变更必须从对应的签名 Release 同步。本文件不得填写尚未真实发布的版本号或日期。

## Unreleased / 未发布

Documentation updates that are not tied to a new installer may land here until the next signed Release.

未绑定新安装包的文档更新可先记在这里，直到下一个签名 Release。

- A confirmed insight declaration is the `@insightBinding` header line in the VBS. `@insightProposal` stays a review comment. Binding index files live in the sibling `Insight Bindings` folder, outside `VBA Script`. `auto` confirmation is rejected. Preview or an explicit confirm still comes before writing.
- Documented the closed `搜索范围` and `搜索对象` values used by command search and insight matching.
- Noted that the public install page can offer a stable even build and a latest trial. The signed installer behavior is unchanged.

- 已确认的洞察声明是 VBS 头部的 `@insightBinding`。`@insightProposal` 仍只是待审注释。绑定索引放在 `VBA Script` 同级的 `Insight Bindings` 目录。`auto` 确认会被拒绝。写入前仍要预演或明确确认。
- 补上命令搜索和洞察匹配使用的封闭 `搜索范围`、`搜索对象` 取值。
- 说明公开安装页可以提供稳定偶数版和最新试用版。已签名安装包的安装行为没有改变。

## [1.0.0.1015] - 2026-10-27

Public GitHub Release: https://github.com/lonardo/clippad_documents/releases/tag/1.0.0.1015

- Fixed clicking a Ribbon search result closing the popup and stopping further typing.
- Fixed Ribbon search results covering the search box.
- Fixed global search and the Ribbon search box opening together.
- Fixed a Word workbench dropdown closing by itself when clicked.
- Fixed a pinned workbench growing wider on every refresh.
- Fixed Smart Suggestions saying the engine was not initialized.
- Added workbench follow-up history, Markdown answers, and text that appears while it is still generating.
- Improved the workbench so it can shrink, a long title is truncated, and the send button stays on screen.
- Improved the command list so a second open does not reread unchanged scripts.
- Improved settings so reopening the page no longer forces a cache bypass.

- 修复点击功能区搜索结果时弹层马上收回、后面无法继续输入的问题。
- 修复功能区搜索结果挡住搜索框的问题。
- 修复全局搜索和功能区搜索框同时打开的问题。
- 修复 Word 工作台里点开下拉列表时，列表自己关掉的问题。
- 修复钉住工作台宽度后，刷新把窗口越撑越宽的问题。
- 修复点击智能建议时提示引擎尚未初始化的问题。
- 新增工作台对话会记住后续上下文，回答可以按 Markdown 显示，并在生成过程中逐步出现。
- 优化工作台窗口可以收到更窄，标题过长时会省略，发送按钮仍留在屏幕上。
- 优化再次打开指令列表时，未改动的脚本不再逐个重读。
- 优化再次打开设置页时不再强制跳过缓存。

### Compatibility / 兼容性

- Windows: desktop Windows with Office 2010 or later, including Microsoft 365 desktop.
- Office: Word, Excel, PowerPoint.
- 32/64-bit: both, matching the installed Office bitness.

### Assets / 发布资产

- OfficeAddinSetup.exe
- SHA256: 215949ce6639fdae3bcf0c0809763c0bb9cd2b1f84be9286c263742f8192c838
- Signature: Valid (Ningbo Wang)

## [1.0.0.1013] - 2026-09-29

- Fixed workbench typing in Word and Excel losing Chinese input, paste, shortcuts, and characters after returning from the document.
- Fixed preview confirmation being covered by the preview.
- Fixed a workbench page that sometimes stayed blank.
- Improved reopening the workbench so it restores the locally saved preview and task note.
- Improved Excel cross-sheet confirmation to one frameless prompt.
- Extended opening an insight in the workbench so it carries the observed selection and operation.
- Added a settings check for whether the insight window can open.

- 修复 Word 和 Excel 工作台输入时中文、粘贴、快捷键丢失，以及从正文回到工作台后字符不在工作台的问题。
- 修复预览确认被预览挡住的问题。
- 修复工作台偶发打开成空白页的问题。
- 优化重新打开工作台时恢复本机保存的预览和任务说明。
- 优化 Excel 跨表核对改为一张无边框确认。
- 拓展从洞察窗口展开到工作台时带上刚才的选区和操作。
- 新增设置里可以检查洞察窗口是否能弹出。

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
