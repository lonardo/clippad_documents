# OfficeAddin 1.0.0.1014 / 发布说明

这是偶数稳定版。安装和升级方式不变。可在插件内检查更新，或从官网下载后覆盖安装。

## 修复与稳定性
- Excel 已确认的洞察绑定会在重复编辑后弹出推荐。
- 已确认绑定不再被评分门槛拦住。重复次数和冷却仍然有效。
- Excel 已绑定推荐不再因没有输入框而弹不出。
- 已绑定推荐不跟随“主动弹出右下角推荐”。关闭一条不会静音其他指令。
- 先预演的指令第一次点击只打开本地计划，确认后才改文档。取消或失败不运行脚本。
- 删除绑定后推荐停止。搜索和工具栏仍可手动运行。
- 关闭 Word、Excel、PowerPoint 不再卡住，也不会退出正在使用的 PowerPoint。PowerPoint 不显示洞察推荐。
- 绑定审阅和推荐按钮提供中英文。
- 工作台已有指令的预演回调已接上，重复预演会合并。
- 细化洞察建议时不再把异常带进脚本正文。
- 功能区下拉框不再抢走搜索焦点。
- Excel 隔离预演保留工作簿原格式。

## 本版带上的已验证能力
- Word 和 Excel 可为本机指令确认洞察触发。确认后的声明写在脚本头部，索引放在脚本目录旁边。
- 模型不能自行写入已确认绑定。未确认建议只留在审阅中。自动确认会被拒绝。
- 写脚本时可以看到已登记的 Excel Host 方法。没有实现的方法不会被写成可调用接口。

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

## English

1.0.0.1014 is a stability release. Install and upgrade behavior is unchanged.

- A confirmed Excel insight binding recommends after repeated edits.
- A confirmed binding is no longer dropped by the score gate. Repeat count and cooldown still apply.
- A bound Excel recommendation appears even when it has no text box.
- A bound recommendation does not follow the generic corner-popup switch. Dismissing one command does not mute the others.
- A preview-first command opens only the local plan on the first click and changes the document after confirm. Cancel or failure does not run the script.
- Removing a binding stops recommendations. Search and the toolbar can still run it.
- Closing Word, Excel, or PowerPoint no longer hangs and does not quit the user's PowerPoint. PowerPoint does not show insight recommendations.
- Binding review and recommendation buttons are available in Chinese and English.
- Existing-command preview callbacks are connected, and repeated preview attempts are coalesced.
- Refining an insight suggestion no longer carries a failure into the script body.
- Ribbon dropdowns no longer take global search focus.
- Isolated Excel preview keeps the workbook's original format.
- Word and Excel can confirm a local insight trigger. The confirmed declaration lives in the script header, and the index lives beside the script folder.
- The model cannot write a confirmed binding. An unconfirmed suggestion stays in review. Automatic confirmation is rejected.
- Registered Excel Host methods are shown to script authors. Methods that are not implemented are not presented as callable.

Installer SHA256: 2eaf84bd93ab651df2300d14b9fb1379e2fbce4b4509987ce1d46f9eb573d6b3
Authenticode: Valid (Ningbo Wang)
