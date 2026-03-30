---
title: "Sandboxing AI Agents, 100x Faster"
source: "https://www.theunwindai.com/p/sandboxing-ai-agents-100x-faster?__readwiseLocation="
author:
  - "[[Shubham Saboo]]"
published: 2026-03-30
created: 2026-03-30
description: "+ Make Claude Code and Codex talk to each other"
tags:
  - "clippings"
---
- [unwind ai 解开 AI。](https://www.theunwindai.com/)
- Posts 职位
- Sandboxing AI Agents, 100x Faster  
	沙箱 AI 代理，快 100 倍

Today’s top AI Highlights:  
今日顶级 AI 亮点：

1. **[Sandboxing AI agents, 100x faster  
	沙盒 AI 代理，快 100 倍](https://blog.cloudflare.com/dynamic-workers/?utm_source=www.theunwindai.com&utm_medium=referral&utm_campaign=sandboxing-ai-agents-100x-faster)**
2. **[Clone any voice in 9 languages 3x faster  
	用9种语言克隆任何声音的速度是3倍](https://console.mistral.ai/build/audio/text-to-speech?utm_source=unwindai&utm_medium=newsletter&utm_campaign=tts)**
3. **[Open-weight agentic search model by Chroma  
	Chroma 的开权重代理搜索模型](https://www.trychroma.com/research/context-1?utm_source=www.theunwindai.com&utm_medium=referral&utm_campaign=sandboxing-ai-agents-100x-faster)**
4. **[Make Claude Code and Codex talk to each other  
	让克劳德代码和法典互相对话](https://github.com/ShawnPana/smux/?utm_source=www.theunwindai.com&utm_medium=referral&utm_campaign=sandboxing-ai-agents-100x-faster)**
5. [**CLI for AI agents to read X, Reddit, YouTube, GitHub - 100% free  
	AI 代理读取 X、Reddit、YouTube、GitHub 的 CLI——100%免费**](https://github.com/Panniantong/Agent-Reach?utm_source=www.theunwindai.com&utm_medium=referral&utm_campaign=sandboxing-ai-agents-100x-faster)

& so much more! 还有更多精彩内容！

***Read time: 3 mins 阅读时间：3分钟***

## AI Tutorial AI 教程

**[How I Built an Autonomous AI Agent Team That Runs 24/7  
我如何组建一支全天候运行的自主 AI 代理团队](https://www.theunwindai.com/p/how-i-built-an-autonomous-ai-agent-team-that-runs-24-7)**

Six AI agents run my entire life while I sleep.  
六个 AI 代理在我睡觉时运行着我的整个生活。

Not a demo. Not a weekend project.  
不是演示。这不是周末的项目。

A real team that works 24/7, making sure I'm never behind. Research done. Content drafted. Code reviewed. Newsletter ready. By the time I open Telegram in the morning, they've already put in a full shift.  
一个真正的团队，全天候工作，确保我永远不会落后。研究已完成。内容已草拟。代码已审查。通讯已准备好。早上我打开 Telegram 时，他们已经下满班了。

By the end of this, you will understand exactly how to build an autonomous AI agent team that runs while you sleep.  
完成这些后，你将完全明白如何组建一支在你睡觉时运行的自主 AI 代理团队。

[![](https://media.beehiiv.com/cdn-cgi/image/format=auto,onerror=redirect/uploads/asset/file/021464df-88a1-4a8d-8905-a1e70c3f2ac4/How_I_Built_an_Autonomous_AI_Agent_Team_That_Runs_247.png)](https://www.theunwindai.com/p/how-i-built-an-autonomous-ai-agent-team-that-runs-24-7)

[How I Built an Autonomous AI Agent Team That Runs 24/7  
我如何组建一支全天候运行的自主 AI 代理团队](https://www.theunwindai.com/p/how-i-built-an-autonomous-ai-agent-team-that-runs-24-7)

[

Full step-by-step tutorial to make your own Agent Team with OpenClaw  
完整的分步教程，如何用 OpenClaw 组建你自己的代理团队

](https://www.theunwindai.com/p/how-i-built-an-autonomous-ai-agent-team-that-runs-24-7)

We share hands-on tutorials like this every week, designed to help you stay ahead in the world of AI. **[If you're serious about leveling up your AI skills and staying ahead of the curve, subscribe now and be the first to access our latest tutorials.](https://www.theunwindai.com/subscribe)**  
我们每周都会分享类似的实践教程，旨在帮助你在人工智能领域保持领先。 **[如果你认真想提升 AI 技能并保持领先，现在就订阅，成为我们最新教程的第一位用户。](https://www.theunwindai.com/subscribe)**

## Latest Developments 最新进展

### Sandboxing AI agents, 100x faster沙盒 AI 代理，快 100 倍

[![](https://media.beehiiv.com/cdn-cgi/image/fit=scale-down,format=auto,onerror=redirect,quality=80/uploads/asset/file/63769704-bc8c-4808-8b7b-ddcfe59cbb75/image.png?t=1774855898)](https://blog.cloudflare.com/dynamic-workers/?utm_source=www.theunwindai.com&utm_medium=referral&utm_campaign=sandboxing-ai-agents-100x-faster)

What if you could spin up a brand-new sandbox for every single user request, run one snippet of AI-generated code, and trash it? All at a million requests per second?  
如果你能为每个用户请求启动一个全新的沙盒，运行一段 AI 生成的代码，然后将其丢弃，会怎样？每秒请求数百万？

That's what Cloudflare just shipped. **Dynamic Worker Loader** is now in open beta, giving any paid Workers user the ability to create V8 isolate sandboxes on the fly, with code specified at runtime.  
这就是 Cloudflare 刚刚发布的产品。 **动态 Worker Loader** 现已进入公开测试阶段，任何付费 Workers 用户都能在运行时指定代码，实时创建 V8 隔离沙盒。

It's the execution layer that Code Mode always needed - isolates that start in milliseconds, use a few megabytes of memory, and run on the same thread as the parent Worker with zero routing latency.  
这是代码模式一直需要的执行层——隔离层起步时间为毫秒，使用几兆字节内存，并且运行在与父工作者同一个线程上，且零路由延迟。

**Key Highlights:主要亮点：**

1. **100x faster than containers**: Isolates boot in single-digit milliseconds vs. hundreds for containers, with 10-100x better memory efficiency. No need to keep warm pools or reuse sandboxes across tasks.  
	**比容器快 100 倍** ：隔离程序启动时间为个位数毫秒，而容器启动时间为数百，内存效率提升 10 到 100 倍。不需要在任务间保留温水池或重复使用沙盒。
2. **Security by default**: Network access is off. Filesystem doesn't exist. Env variables can't leak. Outbound HTTP can be intercepted for credential injection so agents never see secrets.  
	**安全默认：** 网络访问关闭。文件系统不存在。环境变量不会泄漏。出站 HTTP 可以被拦截用于凭证注入，因此代理永远不会看到秘密信息。
3. **TypeScript over OpenAPI**: Agent tools are defined as TypeScript interfaces rather than verbose REST specs, bridged automatically across the sandbox boundary via RPC. The result: dramatically fewer tokens for both the API definition and the agent's code.  
	**OpenAPI 上的 TypeScript** ：代理工具被定义为 TypeScript 接口，而非冗长的 REST 规范，通过 RPC 自动跨越沙盒边界桥接。结果是：API 定义和代理代码的令牌数量都大幅减少。
4. **Production-ready SDK**: `@cloudflare/codemode` ships with `DynamicWorkerExecutor` for plug-and-play sandbox execution, plus server-side utilities to wrap MCP servers or OpenAPI specs into Code Mode tools.  
	**生产准备的 SDK** ： `@cloudflare/codemode` 随 `DynamicWorkerExecutor` 一起出厂，支持即插即用沙盒执行，同时还附带服务器端工具，将 MCP 服务器或 OpenAPI 规范封装进代码模式工具中。

### Voxtral TTS: Clone any voice in 9 languages, at 3x industry speedVoxtral TTS：以工业三倍速度克隆 9 种语言的任何语音

[![](https://media.beehiiv.com/cdn-cgi/image/fit=scale-down,format=auto,onerror=redirect,quality=80/uploads/asset/file/3ea1a4e4-bc9c-4142-8fd4-a8f8a2e9b472/image.png?t=1774855603)](https://console.mistral.ai/build/audio/text-to-speech?utm_source=unwindai&utm_medium=newsletter&utm_campaign=tts)

Just launched: [**Voxtral TTS**](https://console.mistral.ai/build/audio/text-to-speech?utm_source=unwindai&utm_medium=newsletter&utm_campaign=tts) is Mistral's first text-to-speech model, 3x faster than the industry standard, with voice cloning that goes beyond reading text aloud. It models personality: natural pauses, rhythm, intonation, and emotional range.  
刚刚发布： [**Voxtral TTS**](https://console.mistral.ai/build/audio/text-to-speech?utm_source=unwindai&utm_medium=newsletter&utm_campaign=tts) 是 Mistral 首款文本转语音模型，速度是行业标准的三倍，具备超越朗读文本的语音克隆功能。它展现了个性：自然的停顿、节奏、语调和情感范围。

Try it now via API, Mistral Studio, or on Hugging Face under Apache 2.0.  
现在就通过 API、Mistral Studio 或在 Apache 2.0 下的 Hugging Face 上试试。

**Key highlights:主要亮点：**

1. **Human-level naturalness**: Outperforms ElevenLabs Flash v2.5 on naturalness in human evaluations, and matches ElevenLabs v3 quality with emotion-steering for more lifelike, context-aware speech.  
	**人类水平的自然性** ：在人类评估中优于 ElevenLabs Flash v2.5，并在情感引导方面与 ElevenLabs v3 相当，提供更逼真、更具上下文感知的语音。
2. **Voice cloning that captures personality**: Provide a 3-25 second voice prompt and the model replicates not just tone but rhythm, pauses, and emotional dexterity. Zero-shot, no fine-tuning required.  
	**捕捉个性的声音克隆** ：提供一个 3-25 秒的语音提示，模型不仅能模仿语调，还能模仿节奏、停顿和情感灵巧度。零点，无需微调。
3. **9 languages, cross-lingual out of the box**: Supports English, French, German, Spanish, Dutch, Portuguese, Italian, Hindi, and Arabic, including cross-lingual cloning (For example, French voice prompt + English text = English speech with a French accent).  
	9 种 **语言，开箱即** 用：支持英语、法语、德语、西班牙语、荷兰语、葡萄牙语、意大利语、印地语和阿拉伯语，包括跨语言克隆（例如，法语语音提示 + 英语文本 = 带法国口音的英语语音）。
4. **Built for real-time voice agents**: 90ms TTFA with a ~6x real-time factor. Streams natively, handles arbitrarily long generations, and slots into any STT + LLM stack.  
	**为实时语音代理打造** ：TTFA 为 90 毫秒，实时因子约为~6 倍。流原生流，处理任意长的生成，并插入任何 STT + LLM 堆栈。
5. **Full audio pipeline with Voxtral Transcribe**: Pair with Voxtral Transcribe for end-to-end speech-to-speech, or slot into any existing speech-to-text and LLM stack.  
	**与 Voxtral Transcribe 的完整音频流水线** ：与 Voxtral Transcribe 配合进行端到端语音转语音，或插入任何现有的语音转文字和 LLM 堆栈。

[**Try it now!现在就试试吧！**](https://console.mistral.ai/build/audio/text-to-speech?utm_source=unwindai&utm_medium=newsletter&utm_campaign=tts)

### Open-Weight Agentic Search Model by ChromaChroma 的开权重代理搜索模型

[![](https://media.beehiiv.com/cdn-cgi/image/fit=scale-down,format=auto,onerror=redirect,quality=80/uploads/asset/file/b61e894f-6755-4f25-9138-e975160dcbd4/Screenshot_2026-03-30_at_12.20.43_AM.png?t=1774855247)](https://www.trychroma.com/research/context-1?utm_source=www.theunwindai.com&utm_medium=referral&utm_campaign=sandboxing-ai-agents-100x-faster)

The team behind one of the most popular vector databases just shipped their first LLM.  
最受欢迎的向量数据库之一背后的团队刚刚发布了他们的第一个大型语言模型。

Chroma has released **Context-1**, a 20B parameter open-weights model that's trained to do one thing exceptionally well: find the right documents so a bigger model doesn't have to waste time looking.  
Chroma 发布了 **Context-1** ，一个 20B 参数的开放权重模型，训练得非常出色：找到合适的文档，让更大的模型不必浪费时间去寻找。

Context-1 works as a retrieval subagent. You pair it with a frontier reasoning model, and it handles the entire multi-hop search loop autonomously. It decomposes complex queries into subqueries, searches iteratively using hybrid BM25 + dense search, regex, and document reads. And here's the cool part: it actively prunes its own context mid-search, throwing out irrelevant documents to make room for better ones.  
Context-1 作为检索子代理起作用。你把它和前沿推理模型结合起来，它就能自主处理整个多跳搜索循环。它将复杂查询分解为子查询，并通过混合 BM25 + 稠密搜索、正则表达式和文档读取迭代进行搜索。有趣的是：它会主动在搜索中剔除自己的上下文，丢弃无关文档，为更好的文档腾出空间。

The result is frontier-level retrieval performance at 10x the speed and 25x lower cost, released under Apache 2.0 with the full synthetic training pipeline on GitHub.  
结果是实现了前沿级检索性能，速度是前者的 10 倍，成本降低 25 倍，并可在 Apache 2.0 发布，完整合成训练流水线在 GitHub 上发布。

**Key Highlights:主要亮点：**

1. **Self-Editing Context**: Context-1 is trained to selectively discard retrieved documents mid-search with 0.94 prune accuracy, letting a 20B model with a 32k token budget outperform frontier models running on much larger context windows.  
	**自编辑上下文** ：Context-1 训练能在搜索过程中选择性丢弃检索到的文档，修剪准确率为 0.94，使得一个 20 亿个令牌预算的 20 亿美元模型在更大的上下文窗口上表现优于运行在更大上下文窗口上的前沿模型。
2. **Frontier-Competitive Retrieval**: Matches models like GPT-5.4 on benchmarks like BrowseComp-Plus, FRAMES, and HotpotQA, and a 4x parallel config (four agents + reciprocal rank fusion) closes the gap further at a fraction of the compute.  
	前 **沿竞争性检索** ：在 BrowseComp-Plus、FRAMES 和 HotpotQA 等基准测试上匹配 GPT-5.4 等模型，采用 4 倍并行配置（四代理+互惠秩融合），进一步缩小差距，计算量极低。
3. **Staged RL Training**: Fine-tuned from gpt-oss-20B using a curriculum that starts recall-heavy (16x recall over precision) and gradually shifts toward precision, trained on 8,000+ synthetic tasks across web, SEC filings, patents, and email domains.  
	**分阶段强化学习训练** ：从 gpt-oss-20B 微调，课程起初以回忆为重（回忆率 16 倍优先于精准度），逐步转向精准，训练涵盖 8000+个合成任务，涵盖网络、SEC 申请、专利和电子邮件域名。
4. **Fully Open-Source**: Model weights on HuggingFace and the complete synthetic data generation pipeline on GitHub, both under Apache 2.0.  
	**完全开源** ：模型权重在 HuggingFace 上，GitHub 上的完整合成数据生成流水线，均基于 Apache 2.0。

## Quick Bites 快点

[**Local document parsing for AI Agents  
AI 代理的本地文档解析**](https://www.llamaindex.ai/blog/liteparse-local-document-parsing-for-ai-agents?utm_source=www.theunwindai.com&utm_medium=referral&utm_campaign=sandboxing-ai-agents-100x-faster)  
LlamaIndex just open-sourced LiteParse, the core of their LlamaParse engine, stripped down into a fast, local-first CLI and TS-native library for parsing PDFs, Office docs, and images. The interesting bit is that instead of trying to detect tables and convert to markdown (hello, failure modes), it preserves spatial layout on a text grid that LLMs already know how to read. Zero Python dependencies, runs entirely locally, and ships with a ready-made skill for coding agents like Claude Code.  
LlamaIndex 刚刚开源了 LiteParse，这是他们 LlamaParse 引擎的核心，简化为一个快速、本地优先的 CLI 和原生 TS 库，用于解析 PDF、Office 文档和图片。有趣的是，它不是试图检测表格并转换成 markdown（比如失败模式），而是保留了文本网格上的空间布局，而这些网格是大型语言模型已经会读取的。完全没有 Python 依赖，完全本地运行，并且自带了一套现成的 Claude 代码编码代理技能。

[**Use Plugins in Codex for workflows with Skills and integrations  
在 Codex 中使用插件来处理带有技能和集成的工作流程**](https://x.com/OpenAIDevs/status/2037296316104282119?utm_source=www.theunwindai.com&utm_medium=referral&utm_campaign=sandboxing-ai-agents-100x-faster)  
OpenAI's Codex now supports plugins that let you install bundles of skills, MCP servers, and app integrations into a single unit. Think Sentry error logs, Datadog dashboards, and Linear project context flowing directly into your agent's sandbox while it works. You can build custom plugins locally, load them from a repo or personal marketplace, and the official public Plugin Directory is coming soon.  
OpenAI 的 Codex 现在支持插件，允许你将技能包、MCP 服务器和应用集成集成集成到一个单元中。可以想象一下 Sentry 错误日志、Datadog 仪表盘和线性项目上下文，直接流入你代理的沙箱，同时运行。你可以本地构建自定义插件，从仓库或个人市场加载，官方的公开插件目录也即将发布。

[**Quick tips to reduce your Claude Code token usage by upto 60%  
快速建议，帮助你将 Claude Code 代币使用量减少多达 60%**](https://x.com/aibuilderclub_/status/2038174485053046868?s=48&t=7VrJ6DsloavtgAFwEqeQvA&utm_source=www.theunwindai.com&utm_medium=referral&utm_campaign=sandboxing-ai-agents-100x-faster)  
If your Claude Code token bill has been creeping up, this thread walks through a surprisingly effective optimization workflow that can reduce the token usage by upto 60%. The highlights: `/context` reveals how much of your window is gone before you even start (unused MCP servers are the silent culprit), concise CLAUDE.md files and precise prompts shrink search scope, and RTK filters noisy command output before it hits your context. Good quick read.  
如果你的 Claude Code 代币账单一直在上涨，这个帖子会介绍一个出乎意料地有效的优化流程，可以将代币使用量减少多达 60%。重点包括： `/context` 在你开始之前就揭示了窗口已经消失了多少（未使用的 MCP 服务器是无声的罪魁祸首），简洁的 CLAUDE.md 文件和精准提示缩小了搜索范围，RTK 则在命令输出噪杂前过滤掉它进入上下文。读起来很短。

[**Pi: Ollama's take on AI coding agents  
Pi：Ollama 对人工智能编码代理的看法**](https://x.com/ollama/status/2038506792070914079?s=48&t=7VrJ6DsloavtgAFwEqeQvA&utm_source=www.theunwindai.com&utm_medium=referral&utm_campaign=sandboxing-ai-agents-100x-faster)  
Ollama just shipped Pi, a minimal coding agent harness that lets you spin up your own coding agent with a single command. It comes bundled with primitives for building, and supports extensions, skills, prompt templates, and themes, all interoperable between Pi and Ollama. First cloud model out of the gate: Kimi K2.5.  
Ollama 刚刚发布了 Pi，这是一个极简的编码代理框架，让你只需一个命令就能启动自己的编码代理。它自带构建原语，支持扩展、技能、提示模板和主题，所有这些在 Pi 和 Ollama 之间互操作。首款云机型上市：Kimi K2.5。

## Tools of the Trade 行业工具

1. [**Smux**](https://github.com/ShawnPana/smux/?utm_source=www.theunwindai.com&utm_medium=referral&utm_campaign=sandboxing-ai-agents-100x-faster): A tmux configuration that lets AI coding agents collaborate directly in a shared terminal. It turns the terminal into a simple interface where agents like Claude Code and Codex can read each other’s outputs, respond, and work together on tasks without APIs or custom protocols.  
	[**Smux**](https://github.com/ShawnPana/smux/?utm_source=www.theunwindai.com&utm_medium=referral&utm_campaign=sandboxing-ai-agents-100x-faster) ：一种 tmux 配置，允许 AI 编码代理在共享终端中直接协作。它将终端变成一个简单的界面，像 Claude Code 和 Codex 这样的代理可以读取彼此的输出、响应，并在没有 API 或自定义协议的情况下协同完成任务。
2. [**Agent Reach**](https://github.com/Panniantong/Agent-Reach?utm_source=www.theunwindai.com&utm_medium=referral&utm_campaign=sandboxing-ai-agents-100x-faster): A plug-and-play Python toolkit that gives AI agents access to platforms they normally can't reach like X, YouTube, Reddit, Xiaohongshu, Bilibili, and more. It bundles free, open-source tools behind a unified interface so you skip the per-platform config grind and just tell your agent "read this tweet" or "summarize this video."  
	[**Agent Reach**](https://github.com/Panniantong/Agent-Reach?utm_source=www.theunwindai.com&utm_medium=referral&utm_campaign=sandboxing-ai-agents-100x-faster) ：一款即插即用的 Python 工具包，让 AI 代理能够访问通常无法访问的平台，如 X、YouTube、Reddit、小红书、Bilibili 等。它将免费开源工具捆绑在统一界面后面，让你跳过了每个平台的配置繁琐，只需告诉你的客服“阅读这条推文”或“总结这段视频”即可。
3. [**Notchy**](https://x.com/adamlyttleapps/status/2037731313562923121?utm_source=www.theunwindai.com&utm_medium=referral&utm_campaign=sandboxing-ai-agents-100x-faster): A macOS menu bar app that turns your MacBook's notch into a Claude Code terminal. Hover to reveal it, and it auto-detects your open Xcode projects. It also tracks Claude's status live in the notch, plays a sound on task completion, prevents your Mac from sleeping mid-session, and lets you snapshot code with Cmd+S.  
	[**Notchy**](https://x.com/adamlyttleapps/status/2037731313562923121?utm_source=www.theunwindai.com&utm_medium=referral&utm_campaign=sandboxing-ai-agents-100x-faster) ：一款 macOS 菜单栏应用，可以把你的 MacBook 的刘海变成 Claude Code 终端。悬停显示它，它会自动检测你正在进行的 Xcode 项目。它还能实时追踪 Claude 在刘海中的状态，任务完成时播放声音，防止 Mac 在运行中中断，并允许你用 Cmd+S 快照代码。
4. **[Awesome LLM Apps](https://github.com/Shubhamsaboo/awesome-llm-apps?utm_source=www.theunwindai.com&utm_medium=referral&utm_campaign=sandboxing-ai-agents-100x-faster)** - A curated collection of LLM apps with RAG, AI Agents, multi-agent teams, MCP, voice agents, and more. The apps use models from OpenAI, Anthropic, Google, and open-source models like DeepSeek, Qwen, and Llama that you can run locally on your computer.  
	**[超棒的大型语言模型应用](https://github.com/Shubhamsaboo/awesome-llm-apps?utm_source=www.theunwindai.com&utm_medium=referral&utm_campaign=sandboxing-ai-agents-100x-faster)** ——精选的大型语言模型应用合集，包含 RAG、AI 代理、多代理团队、MCP、语音代理等。这些应用使用 OpenAI、Anthropic、Google 以及开源模型如 DeepSeek、Qwen 和 Llama，你可以在电脑本地运行。  
	[(Now accepting GitHub sponsorships)  
	（现接受 GitHub 赞助）](https://sponsorunwindai.com/?utm_source=www.theunwindai.com&utm_medium=referral&utm_campaign=sandboxing-ai-agents-100x-faster)

[![](https://media.beehiiv.com/cdn-cgi/image/fit=scale-down,format=auto,onerror=redirect,quality=80/uploads/asset/file/5842cecc-c30d-48e9-a805-783f55950a3e/image.png?t=1755755385)](https://github.com/Shubhamsaboo/awesome-llm-apps?utm_source=www.theunwindai.com&utm_medium=referral&utm_campaign=sandboxing-ai-agents-100x-faster)

## Hot Takes 热点观点

1. Whoever is taking the time to craft an insanely organized and well-documented Obsidian vault will experience personal AGI faster than anyone else. Arguably months before.  
	凡是花时间打造一个极其有序且文档详尽的黑曜石宝库的人，都会比任何人更快地体验到个人的 AGI。可以说是几个月前。
	~ **[nick vasilescu](https://x.com/nickvasiles/status/2038136699511844951?s=48&t=7VrJ6DsloavtgAFwEqeQvA&utm_source=www.theunwindai.com&utm_medium=referral&utm_campaign=sandboxing-ai-agents-100x-faster)**  
	~ **[尼克·瓦西莱斯库](https://x.com/nickvasiles/status/2038136699511844951?s=48&t=7VrJ6DsloavtgAFwEqeQvA&utm_source=www.theunwindai.com&utm_medium=referral&utm_campaign=sandboxing-ai-agents-100x-faster)**
2. The easiest way to make money fast from a superhuman artificial intelligence would be in the financial markets, almost by definition. So the first lab to develop one, if AGI is possible, would almost certainly keep it quiet for as long as they could. Beats charging for API access  
	从超人人工智能中快速赚钱的最简单方式几乎是金融市场，几乎是必然如此。所以如果 AGI 可能，第一个开发出这种技术的实验室几乎肯定会尽可能长时间保持沉默。比收费 API 访问更划算
	~ **[Ethan Mollick](https://x.com/emollick/status/2038423081606148538?s=48&t=7VrJ6DsloavtgAFwEqeQvA&utm_source=www.theunwindai.com&utm_medium=referral&utm_campaign=sandboxing-ai-agents-100x-faster)**  
	~ **[伊桑·莫利克](https://x.com/emollick/status/2038423081606148538?s=48&t=7VrJ6DsloavtgAFwEqeQvA&utm_source=www.theunwindai.com&utm_medium=referral&utm_campaign=sandboxing-ai-agents-100x-faster)**

That’s all for today! See you tomorrow with more such AI-filled content.  
今天就到这里！明天见，带来更多类似的 AI 内容。

Don’t forget to share this newsletter on your social channels and tag **[Unwind AI](https://www.theunwindai.com/)** to support us!  
别忘了在你的社交频道分享这份通讯，并标记 **[Unwind AI](https://www.theunwindai.com/)** 支持我们！

**PS:** We curate this AI newsletter every day for FREE, your support is what keeps us going. If you find value in what you read, share it with at least one, two (or 20) of your friends 😉  
**附言：** 我们每天都免费策划这份 AI 通讯，你们的支持是我们坚持下去的动力。如果你觉得自己读到的内容有价值，就至少和一两个（甚至二十个）朋友😉分享