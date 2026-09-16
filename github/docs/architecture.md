# Public Architecture Overview / 公共架构概览

This page describes the behavior needed by script authors and users. It intentionally does not publish private C++ implementation details.

本文档只描述脚本作者和用户需要了解的行为，不公开私有 C++ 实现细节。

~~~text
Word / Excel / PowerPoint
          |
          v
OfficeAddin COM Add-in and Ribbon
          |
          +--> command editor and local script registry
          |
          +--> Host runtime
          |       +--> Office context and selection
          |       +--> file, text, clipboard, and path helpers
          |       +--> preview/write-plan/rollback helpers
          |
          +--> workflow dispatcher
          |       +--> local Office action
          |       +--> trusted VBS script
          |       +--> structured execution plan
          |
          +--> optional AI / update / feedback services
~~~

## Host-first boundary / Host-first 边界

The Host object is the stable public boundary for VBS. It provides controlled access to Office objects, current context, local file helpers, clipboard, planning, and result reporting.

Host 对象是 VBS 的稳定公共边界，提供受控的 Office 对象、当前上下文、本地文件辅助、剪贴板、计划和结果报告能力。

The script registry, trust checks, dispatcher, and rollback rules remain product implementation. Public contributors should target the Host contract and not depend on private class names or internal C++ paths.

脚本注册器、信任校验、调度器和回滚规则属于产品实现。公共贡献者应面向 Host 契约，不依赖私有类名或内部 C++ 路径。

## Read, preview, write / 读取、预览、写入

Read operations collect context or produce a report. Preview operations calculate impact without committing. Write operations change a document or local output and require an explicit policy.

读取操作收集上下文或生成报告；预览操作计算影响但不提交；写入操作改变文档或本地输出，需要明确安全策略。

## Optional online services / 可选在线服务

AI, update, feedback, telemetry, VBS market, and account features are separate from the local Host execution path. Their exact network and privacy behavior is release-specific.

AI、更新、反馈、遥测、VBS 市场和账号功能与本地 Host 执行路径分离，具体网络和隐私行为以 Release 为准。
