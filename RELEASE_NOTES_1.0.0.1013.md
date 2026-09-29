# OfficeAddin 1.0.0.1013 / 发布说明

## 重点更新
- Excel 和 Word 的工作台输入更稳：中文输入、粘贴、快捷键，以及从正文回到工作台后，字符留在工作台。
- 预览上方可以直接确认或应用。
- 重新打开工作台时，会尽量恢复上次保存在本机的预览和任务说明。
- 从洞察窗口「在工作台展开」会带上刚才观察到的选区和操作。
- Excel 跨表核对改为一张无边框确认。
- 工作台偶发空白时会尝试恢复页面。
- 设置里可以检查洞察窗口是否能弹出。

## 安装与校验
- 安装包：OfficeAddinSetup.exe
- SHA256：f5715ae301e03305036d8fca1a5f026b262f74481c06e179e621a5171529165a
- MD5：720975d5fe3999b4306e1825542d9ae3
- 签名：Authenticode Valid（Ningbo Wang）
- 支持：Windows 桌面版；Office 2010 及以上；Word / Excel / PowerPoint；具体兼容性以本版本实测为准。

## 已知边界
- 设置里的洞察检查只确认窗口能否弹出。加粗、改颜色这类格式洞察仍依赖实验性格式观察，默认不自动打扰。
- 重要写入操作仍需用户确认。

本版本不上传内部归档 ZIP、PDB 或私有诊断资料。

## English
- Workbench typing in Word and Excel keeps Chinese input, paste, shortcuts, and returned focus in the workbench.
- Preview confirmation stays above the preview.
- Reopening the workbench restores the locally saved preview and task note when that record exists.
- Opening an insight in the workbench carries the observed selection and operation into the task.
- Excel cross-sheet confirmation uses one frameless prompt.
- A blank workbench page attempts to recover instead of staying empty.
- Settings can check whether the insight window can open.

Installer SHA256: f5715ae301e03305036d8fca1a5f026b262f74481c06e179e621a5171529165a
Authenticode: Valid (Ningbo Wang)
