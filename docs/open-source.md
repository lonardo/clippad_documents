# Open-source Boundary / 开源边界

## Community functions repository / 公共函数仓库

The public authoring repository is:

https://github.com/lonardo/clippad_functions

It contains:

- 105 Host-first VBS presets by category;
- Host API v1 JSON;
- VBS examples and safe workflow JSON;
- prompt system instructions and patterns;
- workflow, template, and format-profile schemas;
- scene-profile examples without real documents;
- validation, contribution, testing, privacy, and release documents.

## Apache-2.0 scope / Apache-2.0 范围

VBS, examples, prompts, schemas, and original community documentation in lonardo/clippad_functions are Apache-2.0 unless a file includes a different notice.

lonardo/clippad_functions 中的 VBS、示例、提示词、Schema 和原创公共文档默认采用 Apache-2.0，除非文件另有说明。

The Apache-2.0 license does not grant permission to redistribute modified OfficeAddin installers, product DLLs, trademarks, private backend code, signing material, or online-service credentials.

Apache-2.0 不授予重新分发修改版 OfficeAddin 安装包、产品 DLL、商标、私有后端代码、签名资料或在线服务凭据的权利。

## Contribution boundary / 贡献边界

Contributions must be original or have a compatible license. Do not submit customer documents, real organization templates, private contracts, legal filings, ICP materials, software-copyright materials, patent documents, or production configuration.

贡献必须原创或具有兼容许可证。不得提交客户文档、真实单位模板、私有合同、法律申报、ICP备案、软著、专利或生产配置。

## AI grounding / 大模型约束

AI contributors must read host/host-api-v1.json before generating code. The model must use only listed Host methods, preserve Function Main(), respect UTF-8 BOM, and separate read, preview, and write behavior.

使用大模型贡献代码前必须读取 host/host-api-v1.json。模型只能使用清单中的 Host 方法，保留 Function Main() 和 UTF-8 BOM，并区分读取、预览和写入。

## Release relationship / Release 关系

The functions repository and documents repository may use related version labels, but they are separate artifacts. A product Release must identify the exact community function commit or tag it supports.

公共函数仓库和产品文档仓库可以使用关联版本标签，但它们是独立发布物。产品 Release 必须标明支持的公共函数提交或标签。
