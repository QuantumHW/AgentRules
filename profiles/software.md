# software：软件开发

适用信号：存在源码、构建或依赖配置，且任务涉及实现、调试、测试或维护。仅有一段代码示例不足以认定整个项目是软件项目。

## 引用规则

- 基础：[core](../rules/core.md)、[factual-integrity](../rules/factual-integrity.md)、[scope-control](../rules/scope-control.md)。
- 开发：[anti-overengineering](../rules/anti-overengineering.md)、[error-handling](../rules/error-handling.md)、[technical-accuracy](../rules/technical-accuracy.md)。
- 有代码说明或开发文档任务时，补选 [concise-writing](../rules/concise-writing.md)。

引用是候选集合；按目标项目中实际存在的行为选择条款，不把各文件全文拼接。

## 场景补充

- 从已有源码确定模块职责及扩展位置；没有架构证据时，不规定分层或强制建立目录。
- 保持公开接口与数据格式的已知契约。确需改变时同步直接调用方、相关文档及验证，不额外建设未要求的兼容层。
- 优先使用已有依赖及锁文件流程；新增依赖须解决当前需求，并核查其适用性，不能擅自整体升级工具链。
- 根据改动风险运行已有测试、类型检查或构建。缺陷修复应验证触发路径与必要回归；纯文字、可逆低影响改动不要求新增镜像实现的测试。
- 只有在配置、脚本或维护说明中确认后才写入具体命令；注明必要工作目录。命令存在不等于本次已运行或通过。

## 组合边界

与 documentation 或 academic 组合时，把源码验证限定到相应目录；论文校对不自动要求重构代码，测试通过不构成研究结论的证据。
