# OfficeAddin 1.0.0.1014 / 发布说明

这是偶数稳定版。安装和升级方式不变。可在插件内检查更新，或从官网下载后覆盖安装。

## 修复
- 修复点击字体复选框弹出全局搜索下拉窗口的问题。
- 修复 Excel 重复编辑后，已确认的洞察推荐不出现的问题。
- 修复 Excel 已绑定推荐因为没有输入框而弹不出来的问题。
- 修复关闭“主动弹出右下角推荐”后，已绑定指令也不再提醒的问题，关掉一条不会把其他指令一起静音。
- 修复已确认的洞察绑定因为匹配不够而不出推荐的问题，重复次数和冷却仍然有效。
- 修复删除洞察绑定后仍然继续推荐的问题，搜索和工具栏仍可手动运行。
- 修复关闭 Word、Excel 或 PowerPoint 时卡住的问题，也不会误退出正在使用的 PowerPoint。
- 修复 PowerPoint 误显示洞察推荐的问题。
- 修复工作台里已有指令点预演没有反应的问题，重复点击会合并成一次。
- 修复细化洞察建议失败后，异常文字被写进脚本正文的问题。
- 修复绑定审阅和推荐按钮缺少英文的问题。
- 修复 Excel 隔离预演改变工作簿原格式的问题。

## 优化
- 优化先预演指令的第一次点击：只打开本地计划，确认后才改文档，取消或失败不会运行脚本。

## 新增
- 新增 Word 和 Excel 的本地洞察绑定，确认后写在脚本头部，索引放在脚本目录旁边。模型不能自行写入已确认绑定，未确认建议只留在审阅里，自动确认会被拒绝。

## 拓展
- 拓展写脚本时可见的 Excel Host 方法，只展示已经实现的方法。

## 安装与校验
- 安装包：OfficeAddinSetup.exe
- SHA256：2eaf84bd93ab651df2300d14b9fb1379e2fbce4b4509987ce1d46f9eb573d6b3
- MD5：6bdce3522e32ea972b5a6818be39937a
- 签名：Authenticode Valid（Ningbo Wang）
- 支持：Windows 桌面版；Office 2010 及以上；Word / Excel / PowerPoint。

## 已知边界
- PowerPoint 不提供洞察推荐。保存重复仍只是提示，不会执行。
- 重要写入操作仍需预演或明确确认。

本版本不上传内部归档 ZIP、PDB 或私有诊断资料。

## 文档
- 产品说明：https://github.com/lonardo/clippad_documents
- Host 调用配方：https://github.com/lonardo/clippad_functions/blob/main/docs/host-api.md
- 任务边界：https://github.com/lonardo/clippad_functions/blob/main/prompts/vbs-prompt-patterns.md

## English

1.0.0.1014 is a stability release. Install and upgrade behavior is unchanged.

### Fixed
- Fixed the problem where clicking the font checkbox opened the global search dropdown.
- Fixed confirmed Excel insight recommendations not appearing after repeated edits.
- Fixed bound Excel recommendations failing to appear when they have no text box.
- Fixed bound commands going silent when the generic corner-recommendation switch is turned off. Dismissing one command does not mute the others.
- Fixed confirmed bindings being skipped when the match was not strong enough. Repeat count and cooldown still apply.
- Fixed recommendations that kept appearing after a binding was removed. Search and the toolbar can still run the command.
- Fixed Word, Excel, or PowerPoint hanging on close, and no longer quitting PowerPoint that is still in use.
- Fixed PowerPoint showing insight recommendations.
- Fixed preview of an existing workbench command doing nothing. Repeated clicks are combined into one preview.
- Fixed a failed insight refinement being written into the script body.
- Fixed binding review and recommendation buttons that were missing English.
- Fixed isolated Excel preview changing the workbook's original format.

### Improved
- Improved the first click of a preview-first command: it opens only the local plan, and the document changes after confirm. Cancel or failure does not run the script.

### Added
- Added local insight binding for Word and Excel. A confirmed declaration is written in the script header, and the index sits beside the script folder. The model cannot write a confirmed binding. Unconfirmed suggestions stay in review. Automatic confirmation is rejected.

### Extended
- Extended the Excel Host methods shown while writing scripts. Only implemented methods are shown.

Installer SHA256: 2eaf84bd93ab651df2300d14b9fb1379e2fbce4b4509987ce1d46f9eb573d6b3
Authenticode: Valid (Ningbo Wang)

Documentation:
- Product notes: https://github.com/lonardo/clippad_documents
- Host recipes: https://github.com/lonardo/clippad_functions/blob/main/docs/host-api.md
- Task boundaries: https://github.com/lonardo/clippad_functions/blob/main/prompts/vbs-prompt-patterns.md
