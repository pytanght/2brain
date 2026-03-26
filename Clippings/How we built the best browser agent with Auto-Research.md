---
title: "How we built the best browser agent with Auto-Research"
source: "https://browser-use.com/posts/online-mind2web-benchmark?v=2"
author:
published: 2026-03-25
created: 2026-03-26
description: "97% on Online-Mind2Web benchmark. The highest score ever."
tags:
  - "clippings"
---
![Online-Mind2Web Success Rates](https://browser-use.com/images/benchmark/online_mind2web_styled_v2.png)

## The Benchmark 基准测试

Online-Mind2Web is the most widely reported browser agent benchmark. 300 tasks across 136 real websites - shopping, finance, travel, government, and more. Every web agent is tested on it.  
Online-Mind2Web 是报道最广泛的浏览器代理基准测试。涵盖 136 个真实网站的 300 项任务——购物、金融、旅游、政府管理等。每个网络代理都经过测试。

| Difficulty 难度 | Tasks 任务 | Example 示例 |
| --- | --- | --- |
| Easy 慢点 | 83 | "Open the reviews of a recipe with beef sirloin" - allrecipes.com   “打开牛肉西冷食谱的评测” - allrecipes.com |
| Medium 媒介 | 143 | "Find full-time legal jobs in San Diego County, min $4,000+/month" - ca.gov   “在圣地亚哥县寻找全职法律工作，最低每月 4,000+美元” - ca.gov |
| Hard 非常困难 | 74 | "Find the cheapest hotel + flight + car package from New York to San Francisco, for two adults and a six-year-old child, with free breakfast and spa" - booking.com   “寻找从纽约到旧金山的最便宜酒店+机票+汽车套餐，适合两位成人和一位六岁儿童，含免费早餐和水疗”——booking.com |
| **Total 总计** | **300** |  |

## How Auto-Research for browser agents works浏览器代理的自动研究工作原理

We give Claude Code a CLI to our eval platform and a prompt to run in a loop:  
我们给 Claude Code 一个 CLI 连接到我们的评估平台，并给它一个循环运行的提示：

![Auto-Research Loop](https://browser-use.com/images/benchmark/auto-research-loop-v3.png)

No orchestration code. Each Claude Code session gets a goal and runs 20 cycles on its own. With this [eval infra](https://browser-use.com/posts/our-browser-agent-evaluation-system) we run them in parallel and get a search tree over the space of possible best agents.  
没有编排代码。每个 Claude Code 会话都有一个目标，单独运行 20 个周期。利用 [这个评估基础设施](https://browser-use.com/posts/our-browser-agent-evaluation-system) ，我们并行运行它们，并获得对可能最佳代理空间的搜索树。

![Tree Search Auto-Research](https://browser-use.com/images/benchmark/tree-search-v3.png)

We don't care about low performers. We only care about getting the best agent. So we tell the coding agent to make big bets and avoid small changes, since small tweaks get lost in run-to-run variance.  
我们不关心表现不佳的员工。我们只关心获得最好的代理。所以我们告诉编码代理要大胆押注，避免小改动，因为细微调整会在每次运行的差异中丢失。

## The debugging CLI for deep dives深度挖掘的调试 CLI

One trace can be millions of tokens. That's why we designed the CLI in 3 hierarchical levels to let the agent find root causes as fast as possible.  
一条跟踪可能包含数百万个令牌。这就是为什么我们将 CLI 设计成三层，让代理能尽快找到根因。

![Debugging Loop - Progressive Disclosure](https://browser-use.com/images/benchmark/debugging-loop-v3.png)

TSV over JSON saves 40% of tokens for our data structure. Small format choices can make or break agentic debugging.  
TSV over JSON 为我们的数据结构节省了 40% 的令牌。小格式的选择可以决定代理调试的成败。

![JSON vs TSV format comparison](https://browser-use.com/images/benchmark/tsv-format-v2.png)

## The biggest improvement 最大的改进

Claude Code updated our browser agent harness into a coding agent. Instead of only tools like click and type, it added Python to parse HTML and extract data. This aligns much better with the LLM's training distribution and makes edge cases and data extraction dramatically easier.  
Claude Code 将我们的浏览器代理框架升级为编码代理。它不再只是点击和输入等工具，还加入了 Python 来解析 HTML 和提取数据。这与 LLM 的训练分布更加契合，使边缘情况和数据提取大大简化。

The rest: fixing hundreds of edge cases with the loop.  
剩下的：用循环修复数百个边缘情况。

**What we added:** The [stealthiest browser infrastructure](https://browser-use.com/posts/stealth-benchmark) and every day new tasks our power users ask us to fix. Online-Mind2Web improved as a side effect.  
**我们新增的内容：** [最隐蔽的浏览器基础设施](https://browser-use.com/posts/stealth-benchmark) 和我们高级用户每天要求我们解决的新任务。Online-Mind2Web 作为副作用有所改进。

## The Leaderboard 排行榜

| Agent 代理人 | Score 配乐 | Is Data Public?数据是公开的吗？ | Source 资料来源 |
| --- | --- | --- | --- |
| **Browser Use Cloud (`bu-max`)   浏览器使用云（ `bu-max` ）** | **97%** | ✓ | [GitHub](https://github.com/browser-use/online-mind2web) |
| GPT-5.4 Native Computer Use   GPT-5.4 原生计算机应用 | 93% | ✗ | [Blog](https://openai.com/index/introducing-gpt-5-4/) \* [博客](https://openai.com/index/introducing-gpt-5-4/) \* |
| UI-TARS-2 | 88% | ✗ | [arXiv](https://arxiv.org/abs/2509.02544) |
| ABP + Claude Opus 4.6   ABP + 克洛德作品 4.6 | 86% | ✓ | [GitHub](https://github.com/theredsix/abp-online-mind2web-results) |
| OpenAGI Lux | 84% | ✗ | [Blog 博客](https://www.agiopen.org/blog) |
| TinyFish 小鱼 | 81% | ✓ | [TinyFish blog TinyFish 博客](https://www.tinyfish.ai/blog/mind2web) |
| Navigator (Yutori) 导航员（尤托里） | 79% | ✗ | [Yutori blog Yutori 博客](https://yutori.com/blog/introducing-navigator) |
| ChatGPT Atlas Agent Mode ChatGPT Atlas 代理模式 | 71% | ✗ | [OpenAI blog OpenAI 博客](https://openai.com/index/introducing-gpt-5-4/) |
| Google Gemini CUA 谷歌 Gemini CUA | 69% | ✓ | [Official leaderboard 官方排行榜](https://huggingface.co/spaces/osunlp/Online_Mind2Web_Leaderboard) |
| Stagehand (Gemini 2.5 CU)   舞台工（Gemini 2.5 CU） | 65% | ✓ | [Stagehand evals 舞台工作人员评估](https://www.stagehand.dev/agent-evals) |
| OpenAI Operator OpenAI 操作员 | 61% | ✓ | [Official leaderboard 官方排行榜](https://huggingface.co/spaces/osunlp/Online_Mind2Web_Leaderboard) |
| Claude Sonnet 4.0 CU 克劳德十四行诗 4.0 CU | 61% | ✗ | [OpenAGI blog OpenAGI 博客](https://www.agiopen.org/blog) |
| Stagehand (Sonnet 4.5) 舞台工作人员（十四行诗4.5） | 55% | ✓ | [Stagehand evals 舞台工作人员评估](https://www.stagehand.dev/agent-evals) |

\*OpenAI reported their score without publishing the judge, harness, or task-level results, so independent verification isn't possible.  
\*OpenAI 报告分数时未公布评判、约束或任务级别结果，因此无法进行独立验证。

## The judge matters 法官很重要

The original judge is screenshot-based. But browser agents now write code, call APIs and extract thousands of items. For traditional judges, that's hallucination. If your agentic capabilities increase, you need an agentic judge.  
最初的法官是基于截图的。但现在浏览器代理会编写代码、调用 API，并提取成千上万的项目。对传统法官来说，那是幻觉。如果你的代理能力提升了，你就需要代理法官。

We built an agentic judge on the Claude Agent SDK. We aligned it with human judges, which was key to making the auto-research loop work.  
我们在 Claude Agent SDK 上构建了一个智能法官。我们将其与人类法官对齐，这对实现自动研究循环至关重要。

## Are we overfitting? 我们是不是在过拟合？

The natural tendency of the auto-research loop is to overfit on single tasks. You need to prompt the research system hard to generalize. Most of my time merging cycles is rejecting task-specific solutions that overfit.  
自动研究循环的自然倾向是对单个任务进行过拟合。你需要引导研究系统难以泛化。我合并周期的大部分时间都是拒绝那些任务特定的过拟合解。

We use train/validation splits. The loop only sees training data. We then run on old datasets it has never seen and see score improvements across the board.  
我们使用训练/验证分段。循环只看到训练数据。然后我们运行它从未见过的旧数据集，整体得分都有提升。

## No tasks removed 没有任务被移除

Many companies remove tasks they consider impossible before reporting their score. We use all 300 tasks. Our few failures come from unavailable sites, ambiguous prompts, or websites that changed since the benchmark was created.  
许多公司在报告分数前会删除他们认为不可能完成的任务。我们使用全部300个任务。我们少数的失败来自无法访问的网站、模糊的提示，或自基准建立以来网站发生了变化。

## Rerunning our results is easy重新运行我们的结果很容易

Clone [github.com/browser-use/online-mind2web](https://github.com/browser-use/online-mind2web), set your Browser Use API key, and run.  
克隆 [github.com/browser-use/online-mind2web](https://github.com/browser-use/online-mind2web) ，设置浏览器使用 API 密钥，然后运行。

We also uploaded prompts, results, and judgments.  
我们还上传了提示、结果和评判。

## We need harder benchmarks我们需要更严格的基准

We're building a benchmark with everything users actually care about. Currently benchmarks ignore tasks like: "Extract 1000 products with subpages and compare them across platforms" because it was unimaginable that a single browser agent could do this.  
我们正在构建一个包含用户真正关心的一切的基准测试。目前基准测试忽略了诸如“提取1000个带有子页面的产品并跨平台比较”这样的任务，因为单一浏览器代理无法做到这一点。

Stay tuned.敬请关注。

[Try the best web agent yourself  
自己试试最好的网络代理](https://cloud.browser-use.com/)

[Magnus Müller 马格努斯·穆勒](https://browser-use.com/team/magnus-muller?from=blog) ·