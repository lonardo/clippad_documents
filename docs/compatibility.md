# Compatibility Matrix / 兼容性矩阵

This page records the current public support claim. A Release may narrow the claim for a specific feature; it must not silently expand it without test evidence.

本文档记录当前公开支持口径。某个 Release 可以针对具体功能收窄范围，但没有测试证据时不能自行扩大范围。

## Platform matrix / 平台矩阵

| Platform / 平台 | Status / 状态 | Notes / 说明 |
|---|---|---|
| Windows 10 desktop | Supported public scope | Test the exact Release and Office build |
| Windows 11 desktop | Supported public scope | Test the exact Release and Office build |
| Windows 7 | Not claimed | Do not use old type-library compatibility as a support claim |
| Windows 8/8.1 | Not claimed | No current public Release claim |
| macOS | Not supported | COM add-in and Windows runtime boundary |
| Office for the web | Not supported | Requires installed desktop Office |

## Office matrix / Office 矩阵

| Office family / Office 系列 | Public status / 公开状态 |
|---|---|
| Office 2010 desktop | Tested baseline for the current claim |
| Office 2013 desktop | Included in Office 2010+ compatibility scope; verify Release smoke |
| Office 2016 desktop | Tested and represented by project type-library compatibility |
| Office 2019 desktop | Verify the exact Release smoke result |
| Office 2021 desktop | Verify the exact Release smoke result |
| Microsoft 365 desktop | Verify the exact update channel and Release smoke result |
| Office on the web | Not supported |
| Office for Mac | Not supported |

The project has Office 2010 and Office 2016 type-library compatibility paths. The public product claim is Office 2010 and newer, but feature-level behavior still depends on the application and document.

项目包含 Office 2010 和 Office 2016 类型库兼容路径。公开产品口径为 Office 2010 及以上，但具体功能仍取决于 Office 应用和文档状态。

## Architecture reporting / 位数报告

Report Word, Excel, or PowerPoint architecture as 32-bit, 64-bit, or unknown. Do not infer the add-in architecture from Windows architecture alone.

请报告 Office 为 32 位、64 位或不确定，不要仅根据 Windows 位数推断插件位数。

## Feature-level checks / 功能级检查

The following should be checked separately:

- Ribbon loading and callbacks;
- COM registration and add-in enablement;
- Host context and selection;
- VBS syntax and Host method dispatch;
- Word document operations;
- Excel range and formula operations;
- PowerPoint shape and slide operations;
- preview, commit, rollback, and backup;
- AI gateway, update, feedback, and telemetry behavior.

## Unsupported claims / 不应做出的声明

Do not claim all Office versions, all Windows editions, zero resource usage, no network traffic, legal-format correctness, or guaranteed document preservation without Release-specific evidence.
