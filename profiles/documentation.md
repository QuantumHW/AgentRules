# documentation：通用文档

适用信号：任务围绕指南、手册、报告或模板文档的编写维护。软件仓库仅附带 README 时，按任务需要选择，不必自动叠加完整写作规范。

## 引用规则

- [core](../rules/core.md)、[factual-integrity](../rules/factual-integrity.md)、[scope-control](../rules/scope-control.md)。
- [concise-writing](../rules/concise-writing.md)、[technical-accuracy](../rules/technical-accuracy.md)。
- [current-deliverable](../rules/current-deliverable.md)；已有进度、提交或变更记录要求时补选 [change-traceability](../rules/change-traceability.md)。
- 固定模板或有明确版面要求的格式文件，补选 [template-preservation](../rules/template-preservation.md)。
- 项目以规则、Skill 或文档资源包为版本化产品，或明确要求维护内容版本时，补选 [version-management](../rules/version-management.md)；普通文稿不自动引入产品版本。

## 场景补充

- 从现有文档确定读者、术语、格式及章节职责；遵守有效模板的标题层级、编号和必填区域。
- 保留已有技术观点、专业细节和写作风格，不将结构整理变成未经要求的全文改写；发现疑似错误时指出依据，不在仅排版或检查任务中擅自改变原意。
- 只改用户指定的内容；需要同步图表、目录或交叉引用时，限于保证当前修改一致性的关联部分。
- 使用说明中的路径和命令应与项目一致；不能把演示配置或计划功能写成可直接使用的既有能力。
- 数值、单位、图表、引用与正文对应；重排内容后核对编号及链接。
- 对版面有要求的格式文件，使用可用的目标应用或渲染结果检查实际布局；没有检查就不能声称版面验证通过。

## 组合边界

与 academic 或 proposal 重叠的写作条款合并一次，保留其专属的证据与提交要求。不把软件异常处理规则移植成写作限制。

长期笔记的去重、关联、属性和归档使用 [knowledge-base](knowledge-base.md) 补充；普通文档不因使用 Markdown 就需要笔记元数据、双向链接或知识库权限分区。
