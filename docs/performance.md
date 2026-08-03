# Performance and Resource Use / 性能与资源消耗

## Public claim / 公开口径

OfficeAddin is designed for low resident overhead and minimal disruption to Office work. This is a design goal, not a promise of zero CPU, memory, disk IO, or network activity.

OfficeAddin 的设计目标是低常驻开销、尽量少打扰 Office 工作。这不是“零 CPU、零内存、零 IO 或零网络”的承诺。

The repository does not currently publish a hardware minimum or fixed daily CPU/memory/IO number. The product constraint in engineering guidance is to keep memory usage below 50 MB where practical, but a public guarantee requires Release-specific measurements.

当前仓库不发布硬件最低参数或固定日常 CPU/内存/IO 数值。工程指导要求在可行情况下将内存控制在 50 MB 以下，但公开保证必须以具体 Release 的实测证据为准。

## What affects usage / 影响因素

- Office itself and the opened document;
- active selection size and formula/shape complexity;
- local VBS or workflow batch size;
- preview and history records;
- AI request size and wait time;
- feedback, crash, update, and telemetry settings;
- antivirus, endpoint control, storage, and network latency.

## Release measurement protocol / Release 测量方法

For a future public measurement, record:

1. Windows version and build;
2. Office version, update channel, and 32/64-bit;
3. document size and content shape;
4. idle 10-minute CPU, Working Set, and Private Bytes;
5. selection-change and Ribbon-action peak;
6. read-only VBS, preview, write, batch, and AI scenarios;
7. disk read/write throughput and network wait;
8. p50, p95, peak, sample count, and cleanup result.

后续公开性能数据必须记录 Windows、Office、位数、文档规模、空闲 10 分钟、选区变化、Ribbon 操作、VBS、预览、写入、批处理、AI、IO、网络等待、p50/p95、峰值、样本数和资源释放结果。

## User guidance / 用户建议

- Start with read-only commands.
- Avoid huge batch sizes without a budget or failure plan.
- Close duplicate Office windows and unnecessary add-ins during diagnosis.
- Keep enough disk space for backups and output files.
- Report a reproducible workload instead of saying only “slow” or “high memory”.

建议先运行只读命令；批处理设置数量和失败计划；诊断时关闭多余 Office 窗口和插件；为备份和输出预留磁盘空间；反馈性能问题时提供可复现工作负载。
