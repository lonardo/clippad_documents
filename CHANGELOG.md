# OfficeAddin 1.0.0.1012 / 发布说明

## 重点更新
- Excel 跨表核对候选现在会在上下文稳定且证据充分时显示，确认动作继续严格校验当前工作簿、工作表和选区。
- Excel 启动阶段不再因无工作簿的 UIA provider 阻塞关闭流程，降低启动页卡死风险。
- 洞察提示改为同一文档内重复行为达到阈值后再显示，减少一次性操作造成的打扰。
- Word 格式洞察遵守用户设置，并在重复格式行为达到阈值后提示。

## 安装与校验
- 安装包：OfficeAddinSetup.exe
- SHA256：5d6bfb7c143f60ed28cddbf3edd2e3b5e31053d755e19a3a2e30fd2754bad0af
- MD5：8bc9933268d4600c3621677ecaeb37f9
- 签名：Authenticode Valid（Ningbo Wang）
- 支持：Windows 桌面版；Office 2010 及以上；Word / Excel / PowerPoint；具体兼容性以本版本实测为准。

## 已知边界
- 建议卡片只在上下文和重复行为满足条件时出现；单次格式操作不会触发可见提示。
- 重要写入操作仍需用户确认。

本版本不上传内部归档 ZIP、PDB 或私有诊断资料。

## English
- Excel cross-sheet reconciliation suggestions now appear only with stable context and sufficient evidence; confirmation still validates workbook, sheet, and selection context.
- Excel startup avoids UIA tracking when no workbook exists, reducing close-time hangs on the start page.
- Insights require repeated behavior within the same document before showing a visible prompt.
- Word format insights respect user settings and use the same repeated-behavior threshold.

Installer SHA256: 5d6bfb7c143f60ed28cddbf3edd2e3b5e31053d755e19a3a2e30fd2754bad0af
Authenticode: Valid (Ningbo Wang)