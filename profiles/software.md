# software：软件开发

适用信号：存在源码、构建或依赖配置，且任务涉及实现、调试、测试或维护。仅有一段代码示例不足以认定整个项目是软件项目。

## 引用规则

- 基础：[core](../rules/core.md)、[factual-integrity](../rules/factual-integrity.md)、[scope-control](../rules/scope-control.md)。
- 开发：[anti-overengineering](../rules/anti-overengineering.md)、[error-handling](../rules/error-handling.md)、[technical-accuracy](../rules/technical-accuracy.md)。
- 正式产物与命名：[current-deliverable](../rules/current-deliverable.md)。
- 有界面、错误提示、帮助或开发文档任务时，补选 [concise-writing](../rules/concise-writing.md)。
- 涉及产品版本时选择 [version-management](../rules/version-management.md)；已有进度、Git 或交付流程时按需选择 [change-traceability](../rules/change-traceability.md)。

引用是候选集合；按目标项目中实际存在的行为选择条款，不把各文件全文拼接。

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
