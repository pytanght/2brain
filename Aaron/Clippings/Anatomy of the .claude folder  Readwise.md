---
title: Anatomy of the .claude/ folder | Readwise
source: https://read.readwise.io/new/read/01kmf0mrq515whpps4dp82xg2y
author:
published:
created: 2026-03-25
description: Read and highlight anything
tags:
  - clippings
---
\[译\]如何为你的 AI 劳动力构建操作系统
	 
![](https://pbs.twimg.com/media/HD78D48b0AAI72h.jpg)

**A complete guide to [CLAUDE.md](http://claude.md/), custom commands, skills, agents, and permissions, and how to set them up properly.  
关于 [CLAUDE.md](http://claude.md/) 、自定义命令、技能、代理和权限的完整指南，以及如何正确设置它们。**

---

Most Claude Code users treat the **.claude folder** like a black box. They know it exists. They've seen it appear in their project root. But they've never opened it, let alone understood what every file inside it does.  
大多数 Claude Code 用户把 **.claude 文件夹** 当作黑箱。他们知道它的存在。他们在项目根中看到过这种现象。但他们从未打开过，更别说理解里面每个文件的功能了。

That's a missed opportunity.  
这是个错失的机会。

**The.claude folder is the control center for how Claude behaves in your project.** It holds your instructions, your custom commands, your permission rules, and even Claude's memory across sessions. Once you understand what lives where and why, you can configure Claude Code to behave exactly the way your team needs it to.  
**.claude 文件夹是控制 Claude 在你项目中行为的中心。** 它保存着你的指令、自定义命令、权限规则，甚至克劳德在会话中的记忆。一旦你了解了哪些内容存在于哪里以及为什么，你就可以将 Claude 代码配置成团队所需的完全正确行为。

This guide walks through the entire anatomy of the folder, from the files you'll use daily to the o ⁠⁠  
本指南将详细介绍文件夹的结构，从你每天使用的文件到各个 nes you'll set once and forget. ⁠⁠  
NES 你设置一次就忘了。 ⁠

## Two folders, not one两个文件夹，不是一个

Before diving in, one thing worth knowing upfront: there are actually two.claude directories, not one.  
在开始之前，有一点值得提前知道：实际上有两个.claude 目录，而不是一个。

The first lives inside your project and the second lives in your home directory:  
第一个存储在你的项目中，第二个存储在你的家庭目录中：

![](https://pbs.twimg.com/media/HD70c_tbMAAvhzK.jpg)

**The project-level folder holds team configuration.** You commit it to git. Everyone on the team gets the same rules, the same custom commands, the same permission policies.  
**项目级文件夹存放团队配置。** 你提交到 git 里。团队里每个人都用同样的规则、自定义命令和权限策略。

The global **~/.claude/** folder holds your personal preferences and machine-local state like session history and auto-memory.  
全局 **~/.claude/** 文件夹保存你的个人偏好和机器本地状态，比如会话历史和自动记忆。

## CLAUDE.md: Claude's instruction manualCLAUDE.md：克劳德的说明书

This is the most important file in the entire system. When you start a Claude Code session, the first thing it reads is **[CLAUDE.md](http://claude.md/)**. It loads it straight into the system prompt and keeps it in mind for the entire conversation.  
这是整个系统中最重要的文件。当你启动 Claude Code 会话时，它首先读取的是 **[CLAUDE.md](http://claude.md/)** 。它会直接加载到系统提示中，并在整个对话中牢记。

Simply put: **whatever you write in [CLAUDE.md](http://claude.md/), Claude will follow.**  
简单来说： **无论你 [CLAUDE.md](http://claude.md/) 写什么，Claude 都会跟随。**

If you tell Claude to always write tests before implementation, it will. If you say "never use console.log for error handling, always use the custom logger module," it will respect that every time.  
如果你告诉 Claude 在实现前一定要写测试，它就会做到。如果你说“永远不要用 console.log 来处理错误，务必使用自定义日志模块”，它每次都会尊重这个原则。

A **[CLAUDE.md](http://claude.md/)** at your project root is the most common setup. But you can also have one in **~/.claude/ [CLAUDE.md](http://claude.md/)** for global preferences that apply across all projects, and even one inside subdirectories for folder-specific rules. Claude reads all of them and combines them.  
在项目根点 **[CLAUDE.md](http://claude.md/)** 是最常见的设置。你也可以在 **~/.claude/ [CLAUDE.md](http://claude.md/)** 里设置一个，用于适用于所有项目的全局偏好设置，甚至可以在子目录中设置一个用于文件夹特定规则。克洛德阅读所有这些内容并将它们合并。

What actually belongs in [CLAUDE.md](http://claude.md/)  
什么才真正属于 [CLAUDE.md](http://claude.md/)

Most people either write too much or too little. Here's what works.  
大多数人要么写得太多，要么写得太少。以下是有效的方法。

## Write: 写：

- Build, test, and lint commands (npm run test, make build, etc.)  
	构建、测试和 lint 命令（npm 运行测试，创建构建等）
- Key architectural decisions ("we use a monorepo with Turborepo")  
	关键架构决策（“我们用 monorepo 配合 Turborepo”）
- Non-obvious gotchas ("TypeScript strict mode is on, unused variables are errors")  
	不显而易见的陷阱（“TypeScript 严格模式开启，未使用的变量为错误”）
- Import conventions, naming patterns, error handling styles  
	导入惯例、命名模式、错误处理风格
- File and folder structure for the main modules  
	主要模块的文件和文件夹结构

## Don't write: 不要写：

- Anything that belongs in a linter or formatter config  
	任何属于 linter 或 formatter 配置的配置
- Full documentation you can already link to  
	你已经可以链接的完整文档了
- Long paragraphs explaining theory  
	长段落解释理论

Keep [CLAUDE.md](http://claude.md/) under 200 lines. Files longer than that start eating too much context, and Claude's instruction adherence actually drops.  
保持 [CLAUDE.md](http://claude.md/) 线数在 200 线以下。文件越长就会占用太多上下文，Claude 的指令执行率实际上会下降。

Here's a minimal but effective example:  
这里有一个简约但有效的例子：

```
# Project: Acme API## Commands
npm run dev          # Start dev server
npm run test         # Run tests (Jest)
npm run lint         # ESLint + Prettier check
npm run build        # Production build## Architecture
- Express REST API, Node 20
- PostgreSQL via Prisma ORM
- All handlers live in src/handlers/
- Shared types in src/types/## Conventions
- Use zod for request validation in every handler
- Return shape is always { data, error }
- Never expose stack traces to the client
- Use the logger module, not console.log## Watch out for
- Tests use a real local DB, not mocks. Run \`npm run db:test:reset\` first
- Strict TypeScript: no unused imports, ever
```

That's ~20 lines. It gives Claude everything it needs to work productively in this codebase without constant clarification.  
那是~20 行。它为 Claude 提供了在这个代码库中高效运行所需的一切，无需不断的澄清。

## CLAUDE.local.md for personal overridesCLAUDE.local.md 用于个人覆盖

Sometimes you have a preference that's specific to you, not the whole team. Maybe you prefer a different test runner, or you want Claude to always open files using a specific pattern.  
有时候你的偏好是针对你的，而不是整个团队的。也许你更喜欢不同的测试运行工具，或者你希望 Claude 总是用特定模式打开文件。

Create [CLAUDE.local.md](http://claude.local.md/) in your project root. Claude reads it alongside the main [CLAUDE.md](http://claude.md/), and it's automatically gitignored so your personal tweaks never land in the repo.  
在你的项目根中创建 [CLAUDE.local.md](http://claude.local.md/) 。Claude 会和主 [CLAUDE.md](http://claude.md/) 一起阅读，自动被 git 忽略，所以你的个人修改不会出现在仓库里。

![](https://pbs.twimg.com/media/HD710uUaQAAppSN.jpg)

## The rules/ folder: modular instructions that scale规则/文件夹：可扩展的模块化指令

[CLAUDE.md](http://claude.md/) works great for a single project. But once your team grows, you end up with a 300-line [CLAUDE.md](http://claude.md/) that nobody maintains and everyone ignores.  
[CLAUDE.md](http://claude.md/) 单一项目用得很好。但一旦团队壮大，你最终会得到一个 300 行的管理线 [CLAUDE.md](http://claude.md/) ，没人维护，大家都忽视。

The rules/ folder solves that.  
规则/文件夹解决了这个问题。

**Every markdown file inside.claude/rules/ gets loaded alongside your [CLAUDE.md](http://claude.md/) automatically.** Instead of one giant file, you split instructions by concern:  
**.claude/rules/ 里的每个 markdown 文件都会和 [你的 CLAUDE.md](http://claude.md/) 一起自动加载。** 你不是用一个庞大的文件，而是按关注点划分指令：

```
.claude/rules/
├── code-style.md
├── testing.md
├── api-conventions.md
└── security.md
```

Each file stays focused and easy to update. The team member who owns API conventions edits [api-conventions.md](http://api-conventions.md/). The person who owns testing standards edits [testing.md](http://testing.md/). Nobody stomps on each other.  
每个文件都保持聚焦且易于更新。拥有 API 约定的团队成员负责编辑 [api-conventions.md](http://api-conventions.md/) 。负责测试标准的人会编辑 [testing.md](http://testing.md/) 。没人会互相踩踏。

The real power comes from **path-scoped rules**. Add a YAML frontmatter block to a rule file and it only activates when Claude is working with matching files:  
真正的力量来自 **路径范围的规则** 。在规则文件中添加 YAML 前置块，只有在 Claude 处理匹配文件时才会激活：

```
---
paths:
  - "src/api/**/*.ts"
  - "src/handlers/**/*.ts"
---
# API Design Rules- All handlers return { data, error } shape
- Use zod for request body validation
- Never expose internal error details to clients
```

Claude won't load this file when it's editing a React component. It only loads when it's working inside src/api/ or src/handlers/. Rules without a paths field load unconditionally, every session.  
Claude 在编辑 React 组件时不会加载这个文件。只有在 src/api/ 或 src/handlers/ 中运行时才加载。没有路径的规则场会无条件加载，每次会话。

This is the right pattern once your [CLAUDE.md](http://claude.md/) starts feeling crowded.  
当 [CLAUDE.md](http://claude.md/) 开始感到拥挤时，这就是正确的模式。

## The commands/ folder: your custom slash commands命令/文件夹：你的自定义 slash 命令

Out of the box, Claude Code has built-in slash commands like **/help** and **/compact**. The **commands/** folder lets you add your own.  
开箱即用，Claude Code 内置了 **/help** 和 **/compact** 等斜杠命令。 **命令/** 文件夹允许你添加自己的命令。

**Every markdown file you drop into.claude/commands/ becomes a slash command.  
你把每个 markdown 文件放进.claude/commands 时，都会变成斜杠命令。**

A file named **[review.md](http://review.md/)** creates **/project:review**. A file named [fix-issue.md](http://fix-issue.md/) creates **/project:fix-issue**. The filename is the command name.  
一个名为 **[review.md](http://review.md/)** 的文件创建 **/project：review** 。一个名为 [fix-issue.md](http://fix-issue.md/) 的文件会生成 **/project：fix-issue** 。文件名就是命令名。

![](https://pbs.twimg.com/media/HD72R4zboAEjp6U.jpg)

Here's a simple example. Create **.claude/commands/ [review.md](http://review.md/)**:  
这里有一个简单的例子。创建 **.claude/commands/ [review.md](http://review.md/)** ：

```
---
description: Review the current branch diff for issues before merging
---
## Changes to Review!\`git diff --name-only main...HEAD\`## Detailed Diff!\`git diff main...HEAD\`Review the above changes for:
1. Code quality issues
2. Security vulnerabilities
3. Missing test coverage
4. Performance concernsGive specific, actionable feedback per file.
```

Now run **/project:review** in Claude Code and it automatically injects the real git diff into the prompt before Claude sees it. The **!** backtick syntax runs shell commands and embeds the output. That's what makes these commands genuinely useful instead of just saved text.  
现在用 **Claude Code 运行 /project：review** ，它会自动在 Claude 看到之前将真实的 git diff 注入提示。 **！** backtick 语法运行 shell 命令并嵌入输出。这正是这些命令真正有用的原因，而不仅仅是保存文本。

## Passing arguments to commands将参数传递给命令

Use $ARGUMENTS to pass text after the command name:  
使用$ARGUMENTS 在命令名称后传递文本：

```
---
description: Investigate and fix a GitHub issue
argument-hint: [issue-number]
---
Look at issue #$ARGUMENTS in this repo.!\`gh issue view $ARGUMENTS\`Understand the bug, trace it to the root cause, fix it, and write a
test that would have caught it.
```

Running **/project:fix-issue 234** feeds issue 234's content directly into the prompt.  
运行 **/project：fix-issue 234** 会直接将第 234 期的内容输入提示词。

## Personal vs. project commands个人命令与项目命令

Project commands in **.claude/commands/** are committed and shared with your team. For commands you want everywhere regardless of project, put them in **~/.claude/commands/**. Those show up as **/user:command-name** instead.  
**.claude/commands/** 中的项目命令会提交并与你的团队共享。无论项目如何，你想要的命令都放在 **~/.claude/commands/** 里。这些会显示为 **/user：command-name** 。

A useful personal command: a daily standup helper, a command for generating commit messages following your convention, or a quick security scan.  
一个有用的个人命令：每日站立助手、按惯例生成提交消息的命令，或者快速的安全扫描。

## The skills/ folder: reusable workflows on demand技能/文件夹：按需可重复使用的工作流

You now know how commands work. Skills look similar on the surface, but the trigger is fundamentally different. Here's the distinction before we go any further:  
你现在知道命令是怎么运作的。技能表面上看起来相似，但触发机制本质上不同。在我们继续之前，先区分一下：

![](https://pbs.twimg.com/media/HD73p9-bEAAZUSD.jpg)

**Skills are workflows that Claude can invoke on its own**, without you typing a slash command, when the task matches the skill's description. Commands wait for you. Skills watch the conversation and act when the moment is right.  
**技能是 Claude 可以自行调用的工作流程** ，当任务与技能描述相符时，无需你输入斜杠命令。命令在等你。技能：观察对话，并在合适的时机采取行动。

Each skill lives in its own subdirectory with a [SKILL.md](http://skill.md/) file:  
每个技能都存在于其独立的子目录中，并有一个 [SKILL.md](http://skill.md/) 文件：

```
.claude/skills/
├── security-review/
│   ├── SKILL.md
│   └── DETAILED_GUIDE.md
└── deploy/
    ├── SKILL.md
    └── templates/
        └── release-notes.md
```

The [SKILL.md](http://skill.md/) uses YAML frontmatter to describe when to use it:  
[SKILL.md](http://skill.md/) 使用 YAML 前置说明何时使用：

```
---
name: security-review
description: Comprehensive security audit. Use when reviewing code for
  vulnerabilities, before deployments, or when the user mentions security.
allowed-tools: Read, Grep, Glob
---
Analyze the codebase for security vulnerabilities:1. SQL injection and XSS risks
2. Exposed credentials or secrets
3. Insecure configurations
4. Authentication and authorization gapsReport findings with severity ratings and specific remediation steps.
Reference @DETAILED_GUIDE.md for our security standards.
```

When you say "review this PR for security issues," Claude reads the description, recognizes it matches, and invokes the skill automatically. You can also call it explicitly with **/security-review**.  
当你说“审查此 PR 是否有安全问题”时，Claude 会阅读描述，识别匹配，并自动调用技能。你也可以用 **/security-review** 明确地称呼它。

**The key difference from commands:** skills can bundle supporting files alongside them. The @DETAILED\_GUIDE.md reference above pulls in a detailed document that lives right next to [SKILL.md](http://skill.md/). Commands are single files. Skills are packages.  
**与命令的关键区别在于：** 技能可以将支持文件捆绑在一起。上面@DETAILED\_GUIDE.md 的参考资料拉入了一份详细文档，就放在 [SKILL.md](http://skill.md/) 旁边。命令是单文件。技能是包裹。

Personal skills go in **~/.claude/skills/** and are available across all your projects.  
个人技能可以放在 **~/.claude/skills/** 里，并且在你所有项目中都能找到。

## The agents/ folder: specialized subagent personas代理人/文件夹：专业子代理角色

When a task is complex enough to benefit from a dedicated specialist, you can define a subagent persona in.claude/agents/. Each agent is a markdown file with its own system prompt, tool access, and model preference:  
当任务复杂到需要专门的专家时，你可以在.claude/agents/ 中定义子代理角色。每个代理都是一个 markdown 文件，拥有自己的系统提示符、工具访问和模型偏好：

```
.claude/agents/
├── code-reviewer.md
└── security-auditor.md
```

Here's what a [code-reviewer.md](http://code-reviewer.md/) looks like:  
[code-reviewer.md](http://code-reviewer.md/) 的样子如下：

```
---
name: code-reviewer
description: Expert code reviewer. Use PROACTIVELY when reviewing PRs,
  checking for bugs, or validating implementations before merging.
model: sonnet
tools: Read, Grep, Glob
---
You are a senior code reviewer with a focus on correctness and maintainability.When reviewing code:
- Flag bugs, not just style issues
- Suggest specific fixes, not vague improvements
- Check for edge cases and error handling gaps
- Note performance concerns only when they matter at scale
```

When Claude needs a code review done, it spawns this agent in its own isolated context window. The agent does its work, compresses the findings, and reports back. Your main session doesn't get cluttered with thousands of tokens of intermediate exploration.  
当 Claude 需要进行代码审查时，它会在自己的独立上下文窗口中生成该代理。代理人完成工作，压缩发现，然后反馈。你的主游戏不会被成千上万的中级探索标记所填满。

The tools field restricts what the agent can do. A security auditor only needs Read, Grep, and Glob. It has no business writing files. That restriction is intentional and worth being explicit about.  
工具字段限制了代理的操作。安全审计员只需要 Read、Grep 和 Glob。它不该写文件。这种限制是有意为之，值得明确说明。

The model field lets you use a cheaper, faster model for focused tasks. Haiku handles most read-only exploration well. Save Sonnet and Opus for the work that actually needs them.  
模型字段允许你用更便宜、更快的模型来完成专注任务。Haiku 在大多数只读探索方面表现良好。把十四行诗和 Opus 留给真正需要它们的工作。

Personal agents go in **~/.claude/agents/** and are available across all projects.  
个人经纪人会在 **~/.claude/agents/** 中，所有项目都可以使用。

![](https://pbs.twimg.com/media/HD76U4QbAAAt7X5.jpg)

## settings.json: permissions and project configsettings.json：权限与项目配置

The **settings.json** file inside**.claude/** controls what Claude is and isn't allowed to do. It's where you define which tools Claude can run, which files it can read, and whether it needs to ask before running certain commands.  
**.claude/** 里的 **settings.json** 文件控制 Claude 可以做什么、不能做什么。它就是你定义 Claude 可以运行哪些工具、能读取哪些文件，以及在执行某些命令前是否需要先询问。

The complete file looks like this:  
完整文件如下：

```
{
  "$schema": "https://json.schemastore.org/claude-code-settings.json",
  "permissions": {
    "allow": [
      "Bash(npm run *)",
      "Bash(git status)",
      "Bash(git diff *)",
      "Read",
      "Write",
      "Edit"
    ],
    "deny": [
      "Bash(rm -rf *)",
      "Bash(curl *)",
      "Read(./.env)",
      "Read(./.env.*)"
    ]
  }
}
```

## Here's what each part does.以下是每个部分的作用。

**The $schema line** enables autocomplete and inline validation in VS Code or Cursor. Always include it.  
**$schema 行** 支持自动补全和 VS Code 或光标中的内联验证。一定要包含。

**The allow list** contains commands that run without Claude asking for confirmation. For most projects, a good allow list covers:  
**允许列表** 包含无需 Claude 确认即可运行的命令。对于大多数项目，好的允许清单涵盖：

- Bash(npm run *) or Bash(make* ) so Claude can run your scripts freely  
	Bash（npm 运行 *）或 Bash（制作* ）这样 Claude 就可以自由运行你的脚本
- Bash(git \*) for read-only git commands  
	Bash（git \*） 用于只读 git 命令
- Read, Write, Edit, Glob, Grep for file operations  
	文件操作的读、写、编辑、Glob、Grep

**The deny list** contains commands that are blocked entirely, no matter what. A sensible deny list blocks:  
**拒绝列表** 包含了无论如何都被完全屏蔽的命令。合理的拒绝名单会阻挡：

- Destructive shell commands like rm -rf
- Direct network commands like curl  
	直接网络命令，比如 curl
- Sensitive files like.env and anything in secrets/  
	像.env 这样的敏感文件和任何隐藏在秘密里的东西/

**If something isn't in either list, Claude asks before proceeding.** That middle ground is intentional. It gives you a safety net without having to anticipate every possible command upfront.  
**如果清单上没有，克劳德会先问一声再继续。** 这种中间立场是有意为之。它为你提供了安全网，无需事先预判每一个可能的指令。

## settings.local.json for personal overridessettings.local.json 用于个人覆盖

Same idea as **[CLAUDE.local.md](http://claude.local.md/)**. Create **.claude/settings.local.json** for permission changes you don't want committed. It's auto-gitignored.  
和 **[CLAUDE.local.md](http://claude.local.md/)** 想法一样。创建 **.claude/settings.local.json** 用于你不希望提交的权限更改。它是自动被忽略的。

## The global ~/.claude/ folder全局 ~/.claude/ 文件夹

You don't interact with this folder often, but it's useful to know what's in it.  
你不常接触这个文件夹，但知道里面有什么很有用。

**~/.claude/ [CLAUDE.md](http://claude.md/)** loads into every Claude Code session, across all your projects. Good place for your personal coding principles, preferred style, or anything you want Claude to remember regardless of which repo you're in.  
**~/.claude/ [CLAUDE.md](http://claude.md/)** 会加载到你所有项目的每个 Claude Code 会话中。这里是你个人编程原则、偏好风格或任何你希望 Claude 记住的内容，无论你在哪个仓库里都很好的地方。

**~/.claude/projects/** stores session transcripts and auto-memory per project. Claude Code automatically saves notes to itself as it works: commands it discovers, patterns it observes, architecture insights. These persist across sessions. You can browse and edit them with /memory.  
**~/.claude/projects/** 存储每个项目的会话文字记录和自动记忆。Claude Code 在运行时会自动保存笔记：发现的命令、观察到的模式、架构洞察。这些问题会在多个会话中持续存在。你可以用 /memory 浏览和编辑它们。

**~/.claude/commands/** and **~/.claude/skills/** hold personal commands and skills available across all projects.  
**~/.claude/commands/** 和 **~/.claude/skills/** 在所有项目中都保留了个人命令和技能。

You generally don't need to manually manage these. But knowing they exist is handy when Claude seems to "remember" something you never told it, or when you want to wipe a project's auto-memory and start fresh.  
通常你不需要手动管理这些。但知道它们存在很有用，尤其是当 Claude 似乎“记起”了你从未告诉过的事情，或者你想抹去项目的自动记忆重新开始时。

## The full picture 全貌

Here's how everything comes together:  
以下是所有内容的组成：

```
your-project/
├── CLAUDE.md                  # Team instructions (committed)
├── CLAUDE.local.md            # Your personal overrides (gitignored)
│
└── .claude/
    ├── settings.json          # Permissions + config (committed)
    ├── settings.local.json    # Personal permission overrides (gitignored)
    │
    ├── commands/              # Custom slash commands
    │   ├── review.md          # → /project:review
    │   ├── fix-issue.md       # → /project:fix-issue
    │   └── deploy.md          # → /project:deploy
    │
    ├── rules/                 # Modular instruction files
    │   ├── code-style.md
    │   ├── testing.md
    │   └── api-conventions.md
    │
    ├── skills/                # Auto-invoked workflows
    │   ├── security-review/
    │   │   └── SKILL.md
    │   └── deploy/
    │       └── SKILL.md
    │
    └── agents/                # Specialized subagent personas
        ├── code-reviewer.md
        └── security-auditor.md~/.claude/
├── CLAUDE.md                  # Your global instructions
├── settings.json              # Your global settings
├── commands/                  # Your personal commands (all projects)
├── skills/                    # Your personal skills (all projects)
├── agents/                    # Your personal agents (all projects)
└── projects/                  # Session history + auto-memory
```

## A practical setup to get started一个实用的入门方案

If you're starting from scratch, here's a progression that works well.  
如果你是从零开始，这里有一个很有效的进阶方法。

**Step 1.** Run /init inside Claude Code. It generates a starter [CLAUDE.md](http://claude.md/) by reading your project. Edit it down to the essentials.  
**第一步。** 在 Claude Code 里运行 /init。它通过阅读你的项目生成起始 [的入门 CLAUDE.md](http://claude.md/) 。把内容删减到最要紧要的部分。

**Step 2.** Add.claude/settings.json with allow/deny rules appropriate for your stack. At minimum, allow your run commands and deny.env reads.  
**第二步。** 添加适用于你堆栈的.claude/settings.json 和允许/拒绝规则。至少，允许运行命令并拒绝.env 读取。

**Step 3.** Create one or two commands for the workflows you do most. Code review and issue fixing are good starting points.  
**第三步。** 为你最常用的工作流程创建一个或两个命令。代码审查和问题修复是很好的起点。

**Step 4.** As your project grows and your [CLAUDE.md](http://claude.md/) gets crowded, start splitting instructions into.claude/rules/ files. Scope them by path where it makes sense.  
**第四步。** 随着项目增长， [CLAUDE.md](http://claude.md/) 变得拥挤，开始将指令拆分成.claude/rules/ 文件。按路径规划合适的路径。

**Step 5.** Add a ~/.claude/ [CLAUDE.md](http://claude.md/) with your personal preferences. This might be something like "always write types before implementations" or "prefer functional patterns over class-based."  
**第五步。** 添加一个 ~/.claude/ [CLAUDE.md](http://claude.md/) ，表达你的个人偏好。这可能是“实现前一定要写类型”或者“更倾向于函数式模式而非类型”。

That's genuinely all you need for 95% of projects. Skills and agents come in when you have recurring complex workflows worth packaging up.  
这确实是95%项目所需的全部。技能和经纪人是在你有需要打包的复杂循环工作流程时发挥作用的。

## The key insight 关键见解

The **.claude folder** is really a protocol for telling Claude who you are, what your project does, and what rules it should follow. The more clearly you define that, the less time you spend correcting Claude and the more time it spends doing useful work.  
**.claude 文件夹** 实际上是一个协议，用来告诉 Claude 你是谁，你的项目做什么，以及它应该遵循哪些规则。你越清楚地定义这一点，纠正 Claude 的时间就越少，而它花在有用工作上的时间也越多。

**[CLAUDE.md](http://claude.md/) is your highest-leverage file.** Get that right first. Everything else is optimization.  
**[CLAUDE.md](http://claude.md/) 是你最高杠杆的档案。** 先把这点做好。其他都是优化。

## Start small, refine as you go, and treat it like any other piece of infrastructure in your project: something that pays dividends every day once it's set up properly.从小处开始，边做边完善，把它当作项目中的其他基础设施一样对待：一旦正确设置，每天都能带来回报。

That's a wrap!

If you enjoyed reading this.  
如果你喜欢阅读这篇文章，

Find me → @akshay\_pachaar ✔️  
给我找→ @akshay\_pachaar ✔️

Every day, I share tutorials and insights on AI, Machine Learning and vibe coding best practices.  
每天，我都会分享关于人工智能、机器学习和氛围编码最佳实践的教程和见解。

hidden text to trigger resize events if fonts change  
隐藏文本以触发字体变化时的调整大小事件