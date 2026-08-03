# VBS and Host Guide / VBS 与 Host 指南

## Public repository / 公共仓库

Public VBS, prompts, examples, schemas, Host API JSON, and validation tools are maintained at:

https://github.com/lonardo/clippad_functions

The Host contract is:

https://raw.githubusercontent.com/lonardo/clippad_functions/main/host/host-api-v1.json

生成 VBS 时应先读取 Host API JSON 和公共系统提示词，不要让大模型猜测 COM 方法。

## How the add-in loads VBS / 插件如何加载 VBS

The installed command directory is:

~~~text
<OfficeAddin installation directory>\VBA Script\
~~~

The product script registry discovers trusted script assets and exposes the Host runtime to the executing script. Public source VBS files are UTF-8 BOM. A generated temporary file executed directly by cscript should use UTF-16LE when required by the Windows Script Host environment.

产品脚本注册器发现受信任脚本，并向脚本提供 Host 运行时。公共源 VBS 使用 UTF-8 BOM；如果生成临时文件交给 cscript 直接执行，应按 Windows Script Host 的要求使用 UTF-16LE。

## Entry point / 入口

Public scripts should expose:

~~~vbscript
Function Main()
    Main = "{""ok"":true}"
End Function
~~~

Return a small JSON result with ok, code, message, data, or summary fields. Do not put full customer documents into results or logs.

## Host.GetSelection() / Host.GetSelection()

Host.GetSelection() is usable and read-only. It returns text that the current Host implementation can extract from the current selection and does not open a new selection dialog.

Host.GetSelection() 可用且只读。它返回当前 Host 能从当前选区提取的文本，不会打开新的选择对话框。

- Word: current Selection.Text;
- Excel: scalar text/number from the current Selection Value2; multi-cell arrays are not guaranteed to be expanded;
- PowerPoint: text available from the current ShapeRange.

Use Host.GetSelectionInfo() for structured metadata, Host.GetSelectionObject() for object-level automation, and Host.SelectRange() only when the user must select a new range.

## Write safety / 写入安全

Use this order for write operations:

1. Host.GetRunPreflightPlan or an equivalent context check;
2. Host.GetDocumentInfo, Host.GetSelectionInfo, or app-specific context;
3. Host.ResolveOutputPlan or Host.GetExportPlan;
4. Host.BeginWritePlan and Host.RecordWrite;
5. Host.PreviewWritePlan;
6. user confirmation;
7. Host.ValidateWritePlan;
8. Host.CommitWritePlan;
9. Host.RollbackWritePlan or backup recovery on failure.

## Prohibited public patterns / 公共代码禁止模式

Public Host-first VBS must not use CreateObject, GetObject, WScript.Shell, Shell.Application, ADODB.Stream, FileSystemObject, InputBox, MsgBox, registry access, shell commands, or hidden Office process creation to bypass Host capabilities.

公共 Host-first VBS 不得通过 CreateObject、GetObject、WScript.Shell、Shell.Application、ADODB.Stream、FileSystemObject、InputBox、MsgBox、注册表、Shell 命令或隐藏 Office 进程绕过 Host 能力。
