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

## Excel scene methods / Excel 场景方法

These methods are already registered. A script that looks up columns, reads a table, or writes a result sheet calls them directly. `Host.GetHeaders()` is only the first row of the current selection, joined with `|`.

这些方法已经注册。按表头找列、读表、把结果写到新表时直接调用。`Host.GetHeaders()` 只表示当前选区首行，用 `|` 拼接。

- `Host.ExcelGetHeaderMap([address])` returns `headerMap` with 1-based column numbers. Stop when the needed header is absent.
- `Host.ExcelReadTable([address][, maxRows])` returns TableJson. The default cap is 5000 rows and the hard cap is 20000.
- `Host.ExcelCreateOutputSheet(functionName[, outputMode][, sourceSheet][, create])` plans or creates the result sheet. `create=false` or `plan` returns the planned name only.
- `Host.ExcelPreviewRowSamples`, `Host.ExcelDedupePlan`, `Host.ExcelValidatePlan`, and `Host.ExcelWriteImpactSummary` prepare samples, dedupe plans, validation plans, and impact rows. They do not silently delete or rewrite the source sheet.
- `Host.GetVbaScriptDirectory`, `Host.ResolveVbaScriptPath`, and `Host.ReadVbaScriptLib` read the trusted `VBA Script` root. Absolute paths and `..` are rejected.

`Host.ExcelGetHeaderMap([address])` 返回 `headerMap`，列号从 1 开始。目标表头不在映射里就停止。`Host.ExcelReadTable` 返回 TableJson，默认最多 5000 行，硬上限 20000。`Host.ExcelCreateOutputSheet` 规划或创建结果表；`create` 为 `false` 或 `plan` 时只返回计划名。样本、去重计划、校验计划和影响摘要分别用 `ExcelPreviewRowSamples`、`ExcelDedupePlan`、`ExcelValidatePlan`、`ExcelWriteImpactSummary`，它们不静默删除或改写源表。`GetVbaScriptDirectory`、`ResolveVbaScriptPath`、`ReadVbaScriptLib` 只读受信任的 `VBA Script` 根目录，拒绝绝对路径和 `..`。

Parameter shapes, return fields, and the current reachable patterns for a workbook sheet list and a named chart are in `open_source/docs/host-api.md`. Do not call `Host.ExcelListSheetCatalog`, `Host.ExcelInsertNamedChart`, or `Host.ExcelCreateQueryDraft`. Those names are not registered.

参数、返回字段，以及整本表名和命名图表的当前可达写法，见 `open_source/docs/host-api.md`。不要调用尚未注册的 `Host.ExcelListSheetCatalog`、`Host.ExcelInsertNamedChart`、`Host.ExcelCreateQueryDraft`。

## Insight recommendation / 洞察推荐

An insight may recommend an existing trusted VBS when the current Office app repeats a published scene and a local binding matches that scene. The card is a suggestion. It does not run the script, and it does not write the document until the user previews or confirms.

洞察可以在当前 Office 应用重复出现已发布场景、并且本地绑定对上该场景时，推荐一条已有的受信任 VBS。卡片只是建议。它不运行脚本，也不在用户预演或确认前写入文档。

A script is eligible only when all of these are true:

- It is a first-level file in `VBA Script\*.vbs`, with the required header before any code.
- `适用应用` includes the current app.
- `搜索范围` is one of `无`, `选区`, `当前范围`, `全文`, `指定范围`.
- `搜索对象` is one of `无`, `文本`, `公式`, `图表`.
- A restrictive value is used only when the script cannot do meaningful work outside that scope or object. If the fit is unclear, use `全文` and `无`.
- A confirmed local declaration is one header line, `' @insightBinding {"schemaVersion":1,"policy":"local_trusted","bindings":[...]}`. Copying that `.vbs` carries the declaration.
- Each binding uses a published `triggerId`, an app allowed for that scene, `confirmMode` of `required` or `preview_first`, `minRepeat` of at least 1, and `cooldownSec` of at least 20.
- An index file may also exist at `Insight Bindings\<file>.vbs.binding.json`, beside the `VBA Script` folder. It is not required for a local declaration, and it is not stored inside `VBA Script`.

脚本要能被推荐，必须同时满足：它是 `VBA Script` 根目录的一级 `.vbs`，代码前有必需头部；`适用应用` 包含当前应用；`搜索范围` 只能是 `无`、`选区`、`当前范围`、`全文`、`指定范围`；`搜索对象` 只能是 `无`、`文本`、`公式`、`图表`。只有离开该范围或对象就无法有意义执行时才写限制值。拿不准时用 `全文` 和 `无`。已确认的本地声明是头部一行 `' @insightBinding {"schemaVersion":1,"policy":"local_trusted","bindings":[...]}`。拷贝这个 `.vbs` 会把声明一起带走。每条绑定使用已发布的 `triggerId`、该场景允许的应用、`required` 或 `preview_first`、至少 1 次重复、至少 20 秒冷却。索引可以放在 `VBA Script` 同级的 `Insight Bindings\<文件名>.vbs.binding.json`，本地声明不依赖它，也不放进脚本目录。

`confirmMode` of `auto` is rejected. `preview_first` opens a preview before writing. `required` asks for an explicit confirm. Unknown trigger ids are rejected. Do not invent trigger ids or Host method names to make a recommendation fire.

`confirmMode` 写成 `auto` 会被拒绝。`preview_first` 先打开预演再写入。`required` 要求明确确认。未知 `triggerId` 会被拒绝。不要为了让推荐出现而发明触发编号或 Host 方法名。

Published scenes that a local binding may use:

本地绑定可以使用的已发布场景：

| triggerId | Apps / 应用 | When it can match / 何时可匹配 |
|---|---|---|
| `insight.format.font.bold` | Word | Repeated bold / 短时间重复加粗 |
| `insight.format.font.color` | Word | Repeated font color / 短时间重复改字体颜色 |
| `insight.format.font.size` | Word | Repeated font size / 短时间重复改字号 |
| `insight.format.repeat` | Word, Excel | Repeated formatting / 短时间重复格式调整 |
| `insight.edit.repeat` | Word, Excel | Repeated content edits / 短时间重复编辑内容 |
| `insight.selection.find_replace` | Word, Excel | Repeated selection or find-and-replace / 短时间重复选区或查找替换 |

`insight.document.save.repeat` is published as guidance only. A local binding must not claim it. Save, ribbon, and generic observations stay on the host side.

`insight.document.save.repeat` 只作为提示发布。本地绑定不得声明它。保存、功能区点击和笼统观察仍由宿主处理。

The header comment `@insightProposal` is a review proposal. It never becomes a license, even after a later host update. The host writes `@insightBinding` only after the user confirms. A model must not write `@insightBinding`, and there is no Host method that registers a trigger at runtime. An invalid `@insightBinding` is ignored and does not fall back to an older index. A market declaration may travel in the file, but it does not recommend until this machine has an enable record. A public or market script uses one binding and a cooldown of at least 300 seconds. A local trusted script may declare up to 16 bindings.

头部注释 `@insightProposal` 只是待审建议。即使以后升级宿主，它也不会变成许可。用户确认之后，宿主才写入 `@insightBinding`。模型不要写 `@insightBinding`，也没有运行时自注册的 Host 方法。无效的 `@insightBinding` 会被忽略，不会回退到旧索引。市场声明可以跟着文件走，但本机没有启用记录时不会推荐。准备进入公共或市场分发的脚本只能有一条绑定，冷却至少 300 秒。本地受信任脚本最多声明 16 条绑定。

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
