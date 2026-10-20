[简体中文](README.md) · English

<div align="center">
  <img src="assets/logo.png" width="200" alt="AgentRules Logo">
  <p><strong>Quickly create a tailored AGENTS.md for your project.</strong></p>
  <p>Reusable Rules. Project-Specific Instructions.</p>

  <p>
    <a href="VERSION"><img src="https://img.shields.io/badge/version-1.3.0-1677FF?style=flat-square" alt="Version 1.3.0"></a>
    <a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-22C55E?style=flat-square" alt="MIT License"></a>
  </p>
  <p><a href="#quick-start">Quick Start</a> · <a href="#use-cases">Use Cases</a> · <a href="#how-it-works">How It Works</a> · <a href="#customize">Customize and Update</a></p>
</div>

---

AgentRules combines reusable behavior rules with your project's existing materials and requirements to generate a ready-to-use `AGENTS.md`. It covers software development, documentation, academic papers, project proposals, and personal knowledge bases.

**A lightweight `AGENTS.md` scaffold for project instructions you can continue to refine.**

<a id="quick-start"></a>

## Quick Start

### 1 · Choose an installation method

Both methods use the same `generate-agents` Skill and official built-in rules. Choose one.

**Option A: Standalone Skill**

Send this to an agent with network access and local file permissions:

```text
Install generate-agents from https://github.com/QuantumHW/AgentRules
using Skills CLI at user scope for this agent.
Include the complete Skill directory and references/ resources; do not edit built-in rules.
If an installation already exists, report its status before overwriting it.
Check that the entry point, Rules, and Profiles are readable.
Report the install location and actual results.
```

<details>
<summary>Manual command (requires Node.js / npx)</summary>

```sh
npx skills add QuantumHW/AgentRules --skill generate-agents -g
```

Select your agent when prompted. Add `-a codex` to target Codex only. See [Skills CLI](https://github.com/vercel-labs/skills) for options and updates.

</details>

**Option B: Codex plugin**

Send this to Codex:

```text
Add the plugin marketplace from QuantumHW/AgentRules,
then install agentrules from agentrules-marketplace.
Check its generate-agents Skill and references/ resources, and report the actual result.
```

<details>
<summary>Commands for Codex CLI with plugin support</summary>

```sh
codex plugin marketplace add QuantumHW/AgentRules
codex plugin add agentrules@agentrules-marketplace
```

On supported clients, you can also select the AgentRules marketplace in the plugin directory and install the plugin. Start a new session afterward; discovery depends on the client. See [OpenAI plugin packaging](https://developers.openai.com/plugins/build/plugins).

</details>

This repository provides the Skill package, plugin manifest, and repository marketplace entry. These commands install the version available on GitHub. A repository marketplace does not mean the plugin is listed in the public directory.

### 2 · Generate instructions in your project

Open your project, provide any existing README, requirements, code, templates, or notes, and send:

```text
Use AgentRules to analyze this project
and generate a suitable AGENTS.md.
```

Review the project facts, scope, and verification requirements before using the file for subsequent tasks. With limited information, the workflow produces supported baseline instructions rather than inventing a technology stack or commands.

### 3 · Refine in natural language

```text
Use AgentRules to update the current AGENTS.md.
Preserve handwritten commands and valid project constraints, and merge this request:
This is a research prototype with no legacy compatibility requirements.
Simplify those constraints while keeping necessary correctness and security rules.
```

> **Already have AGENTS.md?** A generation request produces a candidate or diff without overwriting it. Explicit update requests authorize merging; substantive conflicts that cannot be resolved safely require your decision.

<details>
<summary>Explicit Skill invocation</summary>

For a standalone Skill in Codex:

```text
$generate-agents Generate AGENTS.md for this project based on its existing materials.
```

After plugin installation, choose AgentRules' `generate-agents` in the client's Skill picker. If automatic discovery is unavailable, ask the agent to read the installed `SKILL.md` path. Keep the entire Skill directory, not just its entry file.

</details>

<a id="use-cases"></a>

## Use Cases

| Your work | Main focus |
| --- | --- |
| **Software development** | Appropriate design, error handling, scope control, code verification |
| **General documentation** | Accurate content, concise writing, consistent structure and terminology |
| **Academic papers** | Verifiable references, authentic experimental data, supported conclusions |
| **Project proposals** | Template and layout preservation, source verification, aligned tasks, metrics, and outcomes |
| **Personal notes and knowledge bases** | Deduplication and links, properties and tags, archiving and recoverable deletion |

A project can combine multiple contexts. Code, a paper, and a guide can have separate requirements while sharing common constraints.

<details>
<summary>Copy a request for your context</summary>

**Software development**

> Use AgentRules to generate AGENTS.md for this project. Focus on avoiding overengineering, unnecessary exception handling, and feature expansion beyond the requirements.

**General documentation**

> Use AgentRules to generate AGENTS.md for this documentation project. Preserve existing structure and writing style, use consistent terminology, require evidence for technical metrics, and remove process narration that adds no information.

**Academic papers**

> Use AgentRules to generate AGENTS.md for this paper project. Require verifiable data and citations, consistency between results and conclusions, and precise, concise writing that retains necessary conditions and limitations.

**Project proposals**

> Use AgentRules to generate AGENTS.md for this proposal project. Follow the existing template and supporting materials, do not invent research outcomes or technical targets, and keep research tasks aligned with assessment targets.

**Personal notes and knowledge bases**

> Use AgentRules to generate AGENTS.md for this knowledge base. Preserve existing viewpoints and technical details, avoid duplicate notes, follow property, tag, and link conventions, distinguish formal notes from working records, and define authorization boundaries for bulk organization and recoverable deletion.

Knowledge-base fields, heading levels, and paths come from actual project conventions. For a mixed project, add: “Cover the source code, paper, and user guide, distinguishing their scopes.”

</details>

Example outputs: [software project](examples/software/AGENTS.md) · [project proposal](examples/proposal/AGENTS.md) · [personal knowledge base](examples/knowledge-base/AGENTS.md). These use fictional demonstration settings, not your project's configuration.

<a id="how-it-works"></a>

## How It Works

1. **Analyze the project**: Read relevant descriptions, configuration, existing instructions, and task materials to establish the actual context.
2. **Combine rules**: Select behavior Rules and context Profiles, resolving duplication, conflicts, and irrelevant constraints.
3. **Generate instructions**: The `generate-agents` Skill organizes a project-specific `AGENTS.md` and checks facts, scope, and consistency.

The instructions address recurring problems:

- **Overengineering and unjustified defensive code**: Avoid abstractions, compatibility layers, and repeated checks for hypothetical needs; retain handling required at real error boundaries.
- **Fabrication and redundancy**: Do not invent capabilities, data, or references, or present assumptions as facts. Remove empty boilerplate and self-justification.
- **Editing history inside deliverables**: Keep official names and current content, without adding labels such as “simplified edition” or statements announcing deletions.
- **Scope creep**: Preserve valid project instructions and user changes instead of rewriting unrelated content during a task.

The output guides later work; generating it does not itself develop software, edit proposals, or organize real notes. Confirmed product categories, user-specified names, capability limits, and explicitly requested historical materials retain their intended roles.

<a id="customize"></a>

## Customize and Update

Maintainers manage the official Skill, Rules, and Profiles. Installed resources are read-only during ordinary use. Add your requirements when invoking AgentRules; the agent applies them to your project's `AGENTS.md`:

```text
Use AgentRules to generate AGENTS.md for this documentation project.
Preserve the structure and writing style of existing documents.
Do not restructure an entire document unless I explicitly request it.
Apply these requirements to this project without editing AgentRules' built-in resources.
```

For an existing file, explicitly request a merged update that preserves handwritten rules and valid constraints. Earlier project instructions can serve as reference material; their paths, organizations, metrics, and tools do not automatically apply to this project.

Update AgentRules through your chosen installation channel. Skill users can run `npx skills check` first; `npx skills update` updates installed Skills, so review its scope before running it. Plugin users update through the client's plugin update mechanism. Package updates leave existing project `AGENTS.md` files intact. Explicitly request a merged update when you want to apply new rules.

## Usage Notes

- **Review before use**: Instructions provide ongoing guidance; adherence depends on the agent and is not guaranteed.
- **Use project evidence**: Do not invent unknown facts or remove necessary security checks, technical conditions, or factual qualifications for brevity.
- **Follow the tool's loading mechanism**: Rules target agents that support `AGENTS.md`. Skill discovery, invocation, and instruction precedence depend on the tool and require separate platform verification.

## License

AgentRules is available under the [MIT License](LICENSE).
