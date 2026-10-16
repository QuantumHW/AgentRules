[简体中文](README.md) · English

<div align="center">
  <img src="assets/logo.png" width="200" alt="AgentRules Logo">
  <h1>AgentRules</h1>
  <p><strong>Quickly create a tailored AGENTS.md for your project.</strong></p>
  <p>Reusable Rules. Project-Specific Instructions.</p>

  <p>
    <a href="VERSION"><img src="https://img.shields.io/badge/version-1.0.0-1677FF?style=flat-square" alt="Version 1.0.0"></a>
    <a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-22C55E?style=flat-square" alt="MIT License"></a>
  </p>
</div>

---

AgentRules is a lightweight, project-aware scaffolding system for `AGENTS.md`. Using reusable behavior rules and the `generate-agents` Skill, it examines existing project materials and requirements to create clear, ready-to-use AI working instructions that you can refine, reducing repeated prompt writing across projects.

The rules and generated instructions are intended for any agent that can read and follow `AGENTS.md`. Skill installation, discovery, and invocation depend on the tool you use.

## Why AgentRules?

`AGENTS.md` gives supporting agents project-level guidance, including conventions, change boundaries, and verification requirements. Writing it from scratch for every project often means addressing the same problems:

- **Unjustified defensive code**: Broad exception handling, silent fallbacks, or repeated validation for unsubstantiated failure scenarios.
- **Overengineering**: Unrequested abstractions, configuration options, and features that complicate a simple task.
- **Redundant writing**: Process narration, self-justification, and boilerplate that add little information.
- **Fabricated content**: Invented technical details, references, or experimental data, and unverified assumptions presented as facts.
- **Scope creep**: Unrelated file changes and task expansion beyond the original request.

AgentRules turns these recurring issues into reusable rules, selecting and organizing instructions based on project evidence. Necessary error handling, security checks, technical conditions, and real risks remain part of the work.

**Start with instructions tailored to your project, without writing everything from scratch or copying a fixed template.**

## Key Features

### Instructions based on project context

The agent reads relevant project descriptions, directories, dependency configuration, existing instructions, and task materials, then selects rules and resolves duplication and conflicts. Only confirmed technologies, paths, and commands belong in the output. When information is sparse, the workflow produces supported baseline instructions rather than inventing an architecture.

**Rules** organize behavior topics, **Profiles** combine project contexts, and the **Skill** guides analysis, selection, and generation. You do not need to pick and concatenate rule files yourself.

### Multiple project contexts

| Project type | Main focus |
| --- | --- |
| Software development | Avoid overengineering, handle errors appropriately, control scope, verify code behavior |
| General documentation | Accurate content, concise wording, clear structure, consistent terminology |
| Academic papers | Academic expression, verifiable references, consistency between experimental data and conclusions |
| Project proposals | Follow templates, connect technical plans with targets, preserve truthful prior work and outcomes |

A project can combine multiple contexts. When code, a paper, and a guide coexist, their instructions distinguish code verification, research evidence, and document writing while merging shared constraints.

### Preserve existing project instructions

An existing `AGENTS.md` is read in full first. When you explicitly request an update, the workflow preserves valid handwritten rules and project-specific information while integrating applicable instructions. Substantive conflicts that cannot be resolved safely require your decision. A generation request without update authorization produces a candidate or diff rather than overwriting the file.

### Refine rules in natural language

In your local AgentRules repository, describe a problem and the behavior you want to an agent following the repository's maintenance instructions. You can request a merged change or a new rule without learning a configuration language. See “Keep improving your rule library” below.

## Quick Start

### 1. Install

In your agent application, open a session with network access and local file permissions and send:

```text
Install AgentRules from https://github.com/QuantumHW/AgentRules so I can use it across projects with this agent.

Keep the complete repository in a persistent local directory, preserving the relative layout of skills/generate-agents, rules/, and profiles/. Do not copy only SKILL.md.
If this agent supports Agent Skills, register generate-agents using its supported mechanism. Otherwise, provide the local SKILL.md path and explain how to ask this agent to read and follow the workflow directly.
If an installation with the same name already exists, check whether it can be reused rather than overwriting it. Check that the entry point and rule resources are readable, then report the installation location, available invocation method, and actual check results.
```

The agent handles downloading, configuration, and checks; you do not need to clone the repository or run commands manually. Keep the complete repository in place so resource references remain valid. If the workflow is not registered as a Skill, include the local SKILL.md path returned during installation in subsequent requests and ask the agent to read and follow it.

For example, Codex can discover a symlink from `~/.agents/skills/generate-agents` to the repository's `skills/generate-agents` directory; see the [official OpenAI Skill documentation](https://learn.chatgpt.com/docs/build-skills). Other agents use their own configuration mechanisms. Installation and loading require separate verification for each platform.

### 2. Generate AGENTS.md for a project

Open your target project in your agent application, provide any existing README, requirements, source code, templates, or other relevant materials, and enter:

```text
Use AgentRules to analyze this project and generate a suitable AGENTS.md.
```

Tools that support explicit Skill invocation can use their own syntax. For example, in Codex:

```text
$generate-agents Generate AGENTS.md for this project based on its existing materials.
```

The agent follows the workflow to analyze materials, select contexts, and generate instructions. Review the project facts, working boundaries, and verification requirements before using them for subsequent tasks. Empty directories also work, but the Skill will not invent a technology stack or test commands.

### 3. Adjust as needed

Continue with natural-language requests specific to the current project, for example:

> Update the current AGENTS.md: this project is a research prototype with no legacy compatibility requirements. Simplify those constraints while preserving necessary correctness and security requirements.

> Update the current AGENTS.md: this is a formal technical documentation project. Emphasize evidence for technical metrics and remove unnecessary process narration and defensive wording.

To merge updates into an existing file, request this explicitly:

```text
Use AgentRules to update the current AGENTS.md, preserving handwritten commands and project constraints while merging applicable rules.
```

## Usage Examples

### Software development

For a Python web service, constrain implementation and change scope:

> Use AgentRules to generate AGENTS.md for this project. Focus on avoiding overengineering, unnecessary exception handling, and feature expansion beyond the requirements.

Instructions should reflect existing architecture, interfaces, and test entry points. The label “Python web service” alone does not justify inventing a database, directory layout, or deployment workflow.

### Academic papers

For a paper project, express research precisely and concisely:

> Use AgentRules to generate AGENTS.md for this paper project. Require verifiable sources for data and citations, consistency between experimental results and conclusions, and precise, concise academic writing that retains necessary conditions and limitations.

Instructions focus on research evidence and contribution claims. Planned experiments must not become reported results, and passing code tests does not establish a paper's conclusions.

### Project proposals

For a proposal with an existing Word template and supporting materials:

> Use AgentRules to generate AGENTS.md for this proposal project. Follow the existing template and supporting materials, do not invent research outcomes or technical targets, and avoid redundant writing, process narration, and self-justification.

Instructions focus on the template, supporting evidence, and consistency between research tasks and assessment targets. Generating instructions does not itself modify the proposal.

For a mixed project, add “cover the source code, paper, and user guide, distinguishing their scopes.” See the [software example](examples/software/AGENTS.md) and [proposal example](examples/proposal/AGENTS.md); both explicitly use fictional demonstration settings.

## Keep Improving Your Rule Library

Project-specific requirements can be reflected directly in the target project's `AGENTS.md`. For preferences you want to reuse across projects, open the local AgentRules repository created during installation and ask your agent:

> Refine the general documentation rules: when editing an existing document, preserve its structure and writing style unless explicitly asked to restructure the entire document. Check existing rules first to avoid duplication.

The repository's maintenance instructions require the agent to inspect existing content, decide whether to merge, revise, or add a rule, and maintain the relevant Profile references. Describe the problem and desired outcome; you do not need to edit each rule file manually.

This changes your local rule library. It does not automatically publish changes upstream or synchronize instructions already generated for other projects.

## Usage Notes

- **Review the instructions.** `AGENTS.md` provides ongoing guidance; adherence depends on the agent and its instruction-loading mechanism, rather than being guaranteed.
- **Use project evidence.** Unconfirmed technical details, test commands, research results, and project background must not be invented. Concision does not justify removing necessary validation or factual qualifications.
- **Updates are not synchronized automatically.** After changing the local rule library, explicitly request a merged update to each target project's `AGENTS.md` as needed.
- **Distinguish rules from loading support.** The rules target agents that support `AGENTS.md`. Skill discovery, invocation, and instruction precedence depend on the tool; this does not mean every platform has been verified.

## License

AgentRules is available under the [MIT License](LICENSE).
