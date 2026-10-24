# software：软件开发

适用信号：用户明确要求开发软件，需求或设计文档明确描述软件实现目标，或已有源码、构建或依赖配置且任务涉及实现、调试、测试或维护。只有需求文档、尚无工程文件的新项目同样适用。仅有一段代码示例或要求润色技术文档，不足以认定任务是软件开发。

## 引用规则

- 基础：[core](../rules/core.md)、[factual-integrity](../rules/factual-integrity.md)、[scope-control](../rules/scope-control.md)。
- 开发：[anti-overengineering](../rules/anti-overengineering.md)、[error-handling](../rules/error-handling.md)、[technical-accuracy](../rules/technical-accuracy.md)。
- 正式产物与命名：[current-deliverable](../rules/current-deliverable.md)。
- 有界面、错误提示、帮助或开发文档任务时，补选 [concise-writing](../rules/concise-writing.md)。
- 开发协作基线：[change-traceability](../rules/change-traceability.md)、[version-management](../rules/version-management.md)。没有既有流程时也读取其基础条款，具体策略按项目约定或用户选择落实。

引用是候选集合；按目标项目中实际存在的行为选择条款，不把各文件全文拼接。

## 通用开发基线

生成结果须覆盖下列行为主题；可以合并组织，不要求固定章节。适用的基础约束直接写入；策略性选择按 Skill 流程询问用户。不得要求需求文档先写过这些规则才选用。

| 主题 | 必须落实的基础约束 | 规则来源 |
| --- | --- | --- |
| 真实性与范围 | 核对事实和契约，保护用户改动，仅完成当前目标与必要关联修改 | core、factual-integrity、scope-control |
| 设计与依赖 | 沿用有效结构，避免假设需求、重复抽象和无关依赖升级 | anti-overengineering |
| 错误、安全与资源 | 在真实边界校验和处理失败，保护凭据及敏感数据，执行必要资源清理 | error-handling、scope-control |
| 验证与交付 | 按风险验证受影响行为，不编造命令与结果，交付明确未验证项 | technical-accuracy、change-traceability |
| Git 工作边界 | 有仓库时核对状态与差异，保护既有修改，按授权执行写操作与远程操作 | change-traceability |
| 进度与跨会话交接 | 有记录先读，交付说明完成项、验证、未完成项和下一步；需要持久记忆时确认载体 | change-traceability |
| 版本管理 | 核对既有版本策略与来源，区分目标和已发布版本；策略不明时提出选择 | version-management |

Conventional Commits、分支命名、固定进度/记忆文件、SemVer、版本起点与自动版本同步权限属于可选策略，不是既有项目事实。没有仓库时 Git 约束写成条件性规则，不自动初始化；单次脚本或原型可以不建立持久记录与发布体系，但仍保留真实交付及已有版本核对要求。

## 场景补充

- 从已有源码确定模块职责及扩展位置；没有架构证据时，不规定分层或强制建立目录。
- 遵守已确认的平台技术、系统能力、部署范围与兼容策略，不替换既定运行时或用仿制效果冒充指定平台 API。具体框架与系统工具须有目标项目依据，不能从其他项目照搬。
- 涉及用户系统配置、凭据或外部资源时，只使用完成当前任务所需的权限，限定实际修改范围并保留无关的既有配置。
- 保持公开接口与数据格式的已知契约。确需改变时同步直接调用方、相关文档及验证，不额外建设未要求的兼容层。
- 优先使用已有依赖及锁文件流程；新增依赖须解决当前需求，并核查其适用性，不能擅自整体升级工具链。
- 根据改动风险运行已有测试、类型检查或构建。缺陷修复应验证触发路径与必要回归；纯文字、可逆低影响改动不要求新增镜像实现的测试。
- 只有在配置、脚本或维护说明中确认后才写入具体命令；注明必要工作目录。命令存在不等于本次已运行或通过。
- 界面、系统命令、文件、网络或其他真实环境行为按风险进行必要运行验证；构建成功不能代替这些覆盖，缺少环境时如实报告未验证部分。

## 组合边界

与 documentation 或 academic 组合时，把源码验证限定到相应目录；论文校对不自动要求重构代码，测试通过不构成研究结论的证据。
