简体中文 · [English](README_EN.md)

<div align="center">
  <img src="assets/logo.png" width="200" alt="AgentRules Logo">
  <p><strong>快速为你的项目构建专属的 AGENTS.md。</strong></p>
  <p>Reusable Rules. Project-Specific Instructions.</p>

  <p>
    <a href="VERSION"><img src="https://img.shields.io/badge/version-1.3.0-1677FF?style=flat-square" alt="Version 1.3.0"></a>
    <a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-22C55E?style=flat-square" alt="MIT License"></a>
  </p>
  <p><a href="#quick-start">快速开始</a> · <a href="#use-cases">适用场景</a> · <a href="#how-it-works">工作方式</a> · <a href="#customize">定制与更新</a></p>
</div>

---

AgentRules 根据项目已有资料和你的工作要求，组合适用的行为规则，生成可直接使用的 `AGENTS.md`。适用于软件开发、文档、科研论文、项目申报书和个人知识库。

**一个轻量级的 `AGENTS.md` 智能脚手架，为项目建立可继续完善的基础规范。**

<a id="quick-start"></a>

## 快速开始

### 1 · 选择安装方式

两种方式使用同一份 `generate-agents` Skill 和官方内置规则，任选一种即可。

**方式 A：独立 Skill**

在支持联网和本地文件操作的 Agent 会话中，复制发送：

```text
请从 https://github.com/QuantumHW/AgentRules 安装 generate-agents Skill，
使用 Skills CLI 按当前 Agent 类型安装到用户级目录。
完整安装该 Skill 目录及 references/ 资源，不修改内置规则。
若已有同名安装，先报告状态，不直接覆盖。
完成后检查入口、Rules 和 Profiles 可读，报告安装位置和实际结果。
```

<details>
<summary>手动安装命令（需要 Node.js / npx）</summary>

```sh
npx skills add QuantumHW/AgentRules --skill generate-agents -g
```

按提示选择所用 Agent。仅安装到 Codex 可追加 `-a codex`。参数与更新方式见 [Skills CLI](https://github.com/vercel-labs/skills)。

</details>

**方式 B：Codex 插件**

向 Codex 发送：

```text
请从 QuantumHW/AgentRules 添加插件市场，
并安装其中的 agentrules 插件（市场名 agentrules-marketplace）。
检查插件内的 generate-agents Skill 和 references/ 资源，报告实际安装结果。
```

<details>
<summary>支持插件功能的 Codex CLI 安装命令</summary>

```sh
codex plugin marketplace add QuantumHW/AgentRules
codex plugin add agentrules@agentrules-marketplace
```

也可在支持该市场的客户端插件目录中，选择 AgentRules 市场并安装插件。安装后开启新会话；目录显示与加载方式取决于客户端。规范见 [OpenAI 插件打包文档](https://developers.openai.com/plugins/build/plugins)。

</details>

本仓库提供 Skill 包、插件清单和仓库市场入口。以上命令获取 GitHub 上已推送的版本；仓库市场入口不代表已上架公共插件目录。

### 2 · 在目标项目生成

打开你的项目，提供已有 README、需求、源码、模板或笔记，然后发送：

```text
使用 AgentRules，分析当前项目，
并为我生成一份适用的 AGENTS.md。
```

审阅生成文件中的项目事实、工作范围和验证要求，即可用于后续任务。信息不足时，只生成有依据的基础约束，不补造技术栈或命令。

### 3 · 继续用自然语言调整

```text
使用 AgentRules 更新当前 AGENTS.md。
保留手工编写的命令和有效项目约束，合并以下要求：
这个项目用于科研原型验证，没有历史版本兼容要求；
请精简相关约束，保留必要的正确性和安全要求。
```

> **已有 AGENTS.md？** 仅请求“生成”时提供候选或差异，不直接覆盖；明确要求更新后才合并。无法安全解决的实质冲突由你决定。

<details>
<summary>显式调用 Skill</summary>

独立 Skill 在 Codex 中可显式调用：

```text
$generate-agents 为当前项目生成 AGENTS.md，以现有资料为依据。
```

插件安装后，可在客户端的 Skill 选择器中选择 AgentRules 提供的 `generate-agents`。不支持自动发现时，让 Agent 读取安装时返回的 `SKILL.md` 路径；需要整个 Skill 目录，不能只复制入口文件。

</details>

<a id="use-cases"></a>

## 适用场景

| 你在做什么 | 规范重点 |
| --- | --- |
| **软件开发** | 设计适度、异常处理、修改范围、代码验证 |
| **通用文档** | 内容准确、表达精练、结构与术语一致 |
| **科研论文** | 引用可核验、实验数据真实、结论有依据 |
| **项目申报书** | 模板与版面保护、来源核验、任务—指标—成果对应 |
| **个人笔记与知识库** | 去重与关联、属性和标签、归档与可恢复删除 |

一个项目可组合多个场景。例如源码、论文与手册共存时，分别规定各自要求，合并共通约束。

<details>
<summary>复制场景化请求</summary>

**软件开发**

> 使用 AgentRules 为当前项目生成 AGENTS.md。重点约束过度设计、无意义的异常处理，以及超出需求的功能扩展。

**通用文档**

> 使用 AgentRules 为当前文档项目生成 AGENTS.md。保留已有结构和写作风格，统一术语，要求技术指标有依据，删除无信息的过程性表达。

**科研论文**

> 使用 AgentRules 为当前论文项目生成 AGENTS.md。要求数据和引用可核验、实验结果与结论一致，表达准确精练，保留必要的条件与局限。

**项目申报书**

> 使用 AgentRules 为当前申报书项目生成 AGENTS.md。遵守现有模板和补充资料，不编造研究成果或技术指标，保持研究内容与考核指标一致。

**个人笔记与知识库**

> 使用 AgentRules 为当前知识库生成 AGENTS.md。保留已有观点和专业细节，避免重复建页，遵守属性、标签和链接约定，区分正式笔记与工作记录，明确批量整理和可恢复删除的授权边界。

知识库的字段、标题层级和路径来自实际约定，不强加其他项目的设置。混合项目可以补充：“同时覆盖源码、论文和使用手册，并区分各自作用范围。”

</details>

参考生成结果：[软件项目](examples/software/AGENTS.md) · [项目申报书](examples/proposal/AGENTS.md) · [个人知识库](examples/knowledge-base/AGENTS.md)。这些示例采用虚构演示背景，不代表你的项目配置。

<a id="how-it-works"></a>

## 工作方式

1. **分析项目**：读取相关说明、配置、现有指令和任务材料，确认实际上下文。
2. **组合规则**：从行为规则（Rules）与场景配置（Profiles）中筛选内容，处理重复、冲突和不适用条款。
3. **生成规范**：由 `generate-agents` Skill 组织为项目专属 `AGENTS.md`，核查事实、范围和一致性。

规范重点约束这些反复出现的问题：

- **过度设计与防御**：不为假设需求增加抽象、兼容层或重复校验；保留真实错误边界所需的处理。
- **失真与冗余**：不编造功能、数据或文献，不将推测写成事实；删去无信息的套话与自我辩解。
- **成品夹带修改过程**：沿用正式名称，直接呈现当前内容，不因删改新增“精简版”等标签或删除声明。
- **修改范围失控**：保留有效项目约束和用户改动，不因一次任务顺带重写无关内容。

生成的是后续工作的指导文件，不会因此执行软件开发、修改申报书或整理真实笔记。正式分类、用户指定名称、能力限制与明确要求的历史材料仍按其用途处理。

<a id="customize"></a>

## 定制与更新

官方 Skill、Rules 和 Profiles 由维护者统一维护，安装后默认只读使用。你只需在调用时补充需求，Agent 会将其落实到目标项目的 `AGENTS.md`：

```text
使用 AgentRules 为当前文档项目生成 AGENTS.md。
修改已有文档时保留原有结构和写作风格；
除非我明确要求，否则不要重构整篇文档。
这些要求只用于当前项目，不修改 AgentRules 内置资源。
```

已有文件时，明确要求“更新并合并”，保留手工规则与有效约束。也可提供旧项目规范作为参考；旧项目的路径、组织、指标和工具不自动成为当前项目事实。

通过安装时所选渠道更新 AgentRules。Skill 用户可先用 `npx skills check` 检查更新；`npx skills update` 会更新已安装的 Skills，执行前应确认影响范围。插件用户通过客户端的插件更新机制升级。安装包更新后，已有项目的 `AGENTS.md` 保持原样；需要应用新规则时，再明确请求合并更新。

## 使用须知

- **先审阅再使用**：规范提供持续指导，实际遵守程度取决于 Agent，不是执行保证。
- **以项目证据为准**：未知事实不补造，必要的安全校验、技术条件与事实限定不能因精简而删除。
- **按工具加载**：规则面向支持 `AGENTS.md` 的 Agent；Skill 的发现、调用及指令优先级取决于工具，各平台需分别验证。

## 开源协议

AgentRules 采用 [MIT License](LICENSE) 开源协议。
