# 1008 稳定性与消息中心服务更新 / 1.0.0.1008 Stabilization Service Update

发布日期 / Published: 2026-08-17
范围 / Scope: 配套现有 `1.0.0.1008` 客户端的服务端与稳定性更新。此页不是新的客户端安装包 Release。
This page describes service-side and stability work accompanying the existing `1.0.0.1008` client. It is not a new client installer Release.

## 面向用户的变化 / User-visible changes

- AI 工作台首次打开、空白窗口恢复和网页窗口响应路径得到加固。
- 设置页首屏加载更轻，工具栏目录采用延迟加载，减少首次打开等待。
- 消息中心支持反馈/崩溃处理进展消息；Ribbon 工具栏显示“新消息”，设置页消息 tab 显示未读提示，点击提醒可直接进入消息中心。
- 启动后会延迟检查消息，避免阻塞 Office 启动；消息中心和错误状态提供中英文文案。
- Crash 处理遵循服务端策略，并在上传上下文中继续脱敏用户路径；未知策略默认收敛到更小的诊断范围。

- The AI workbench now has stronger first-open, blank-window recovery, and web-window response paths.
- Settings opens with less work on the first screen; the toolbar catalog is loaded lazily to reduce initial waiting.
- The inbox can show feedback/crash progress messages. The Ribbon exposes a visible “新消息 / New message” reminder, the Settings message tab shows unread state, and the reminder opens the message center directly.
- Inbox polling is delayed after Office startup so it does not block startup; message-center and error states have Chinese and English copy.
- Crash handling follows the server policy and continues to redact user paths from upload context; unknown policy falls back to a narrower diagnostic scope.

## 发布边界 / Release boundary

本次不改变客户端四段版本号、安装包、生产升级清单或签名资产。用户仍应以当前官方 Release 页面中的 `1.0.0.1008` 安装包和校验值为准；后续客户端安装包会在完成独立的 staging、构建、签名和人工验收后另行发布。

This update does not change the four-part client version, installer, production upgrade manifest, or signing assets. Users should continue to use the `1.0.0.1008` installer and checksum from the current official Release page. A client package will be published separately after its own staging, build, signing, and manual acceptance gates pass.

## 安全与隐私 / Security and privacy

公开页面不会包含客户端 token、私有接口、内部主机名、崩溃转储或用户文档。消息拉取使用每个客户端自己的安装标识和受保护的服务端通道；未配置服务端凭据的客户端不会被当作已认证客户端处理。

Public pages do not contain client tokens, private endpoints, internal hostnames, crash dumps, or user documents. Inbox pulls use the client installation identity and a protected server channel; a client without the configured server credential is not treated as authenticated.

## 相关入口 / Related links

- 官网发布事实 / Official release facts: <https://clippad.vip/docs/release.md>
- 官网论坛 / Official forum: <https://clippad.vip/community>
- 客户端安装与校验 / Client installation and verification: <https://github.com/lonardo/clippad_documents/releases>
