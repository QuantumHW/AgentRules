# knowledge-base：个人笔记与知识库

适用信号：任务涉及长期笔记整理、概念关联、标签属性、知识归档或知识库维护；可来自明确的用户目标、已有笔记规范、模板、索引或 Obsidian 等知识库结构。单个 Markdown 文件、软件手册或仅提到 Obsidian 不足以启用整套约束。

## 引用规则

- [core](../rules/core.md)、[factual-integrity](../rules/factual-integrity.md)、[scope-control](../rules/scope-control.md)。
- [knowledge-organization](../rules/knowledge-organization.md)、[concise-writing](../rules/concise-writing.md)。
- [current-deliverable](../rules/current-deliverable.md)；已有阶段、Git 或变更记录约定时补选 [change-traceability](../rules/change-traceability.md)。
- 科研或技术笔记需要核对方法、公式与技术含义时，补选 [technical-accuracy](../rules/technical-accuracy.md)。

## 场景补充

- 按需查看现有维护说明、笔记模板、标签索引和少量相关笔记，确认实际约定。不要为了生成规范遍历全部私人笔记、读取无关日记或修改知识资产。
- 输出应明确已确认的正式归档区、Agent 工作区、标签索引、回收站及规则文件审批边界。未确认时不编造路径、不新设工作区，也不授予其自动写入权限。
- 对已有笔记遵守原有结构、专业表达和术语；默认语言取自项目约定或用户请求，必要时保留英文术语及首次释义，不将某个个人库的中文偏好强制用于其他知识库。

### Obsidian 与模板约定

- 已有规范或模板明确“文件名承担一级标题”时，笔记正文从自然段或 `##` 开始，不重复添加 `#`，后续标题保持连续。不能仅凭使用 Obsidian 就认定所有笔记都必须省略一级标题；该约定也不自动约束 `AGENTS.md`、模板代码块或其他产物。
- 已采用 Obsidian 双向链接时沿用 `[[目标]]`，按实际需要使用标题、块与别名，不将普通 Markdown 项目强行转换为 Wiki 链接。
- 已约定 `tags`、`date`、`describe` 时，新建笔记使用这些字段；获授权整理的笔记缺失字段时按实际内容补齐。`tags` 使用 YAML 列表，`date` 保留首次创建时间，`describe` 只概括已有内容；未知时间和空白内容允许留空，不使用范例日期或当前时间冒充首次创建时间。有更高精度要求但证据不足时报告缺口。
- 尊重其他模板的 `description`、`created` 等合法字段及插件属性，不自动改名。现有字段的含义不明确时先核实，不按名称猜测时间语义。
- 已确认采用库内 `.trash/` 回收站时，删除默认移入该目录并避免重名覆盖；不因发现 `.obsidian/` 就假定回收站配置，也不清空回收站。
- 类似 `Agent-Workspace/`、标签索引路径和受保护指令文件，只在目标项目明确采用时写入输出。对必须先审批的规则文件保留审批要求；新增正式笔记的授权不扩展为修改周边笔记或权限规则的授权。

## 组合边界

可与 documentation 组合补充格式与写作，与 academic 组合处理科研笔记的引用和实验依据；合并重复的事实、范围和表达条款。软件项目只在独立笔记区域确有维护任务时局部采用本 Profile，不把属性补齐、回收站或无一级标题规则传播到源码和普通 README。
