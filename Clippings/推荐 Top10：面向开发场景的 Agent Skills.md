---
title: "Thread by @shao__meng"
source: "https://x.com/shao__meng/status/2036805560859808083"
author:
  - "[[@shao__meng]]"
published: 2026-03-25
created: 2026-03-26
description:
tags:
  - "clippings"
---
**meng shao** @shao\_\_meng [2026-03-25](https://x.com/shao__meng/status/2036805560859808083)

推荐 Top10：面向开发场景的 Agent Skills  
  
这次 Top10 Skills 选择优先考虑可信来源、跨项目复用和对开发闭环的直接增益。筛出的核心能力集中在系统接入、浏览器执行、本地验证、计划管理、CI 修复与工作流沉淀，适合长期作为 Codex / Claude Code 等的开发增强配置。  
  
1\. mcp-builder

用于指导构建 MCP 服务器，重点覆盖工具设计、协议理解、接口封装与可供 agent 使用的服务接入实践。

https://github.com/anthropics/skills/tree/main/skills/mcp-builder…  
  
2\. playwright

浏览器自动化是开发 agent 的标准执行层之一，适合调试、复现、抓取、截图、验收。

https://github.com/openai/skills/tree/main/skills/.curated/playwright…  
  
3\. webapp-testing

对本地 web 应用验证特别实用，比通用浏览器 skill 更贴近日常开发排错。

https://github.com/anthropics/skills/tree/main/skills/webapp-testing…  
  
4\. skill-creator

复利最高。能把高频 prompt 和流程沉淀成可复用 skill。

https://github.com/anthropics/skills/tree/main/skills/skill-creator…  
  
5\. create-plan

对复杂开发任务很有价值，能把“直接写代码”拉回到可执行计划和边界管理。

https://github.com/openai/skills/tree/main/skills/.curated/create-plan…  
  
6\. gh-fix-ci

修 CI 是极高频开发痛点，这个 skill 命中非常准确。

https://github.com/openai/skills/tree/main/skills/.curated/gh-fix-ci…  
  
7\. gh-address-comments

适合 PR review 闭环，把“看评论 -> 改代码 -> 回应 review”串起来。

https://github.com/openai/skills/tree/main/skills/.curated/gh-address-comments…  
  
8\. security-best-practices

在开发场景里很值得装。它不一定天天触发，但一旦用上，价值很高。

https://github.com/openai/skills/tree/main/skills/.curated/security-best-practices…  
  
9\. vercel-react-best-practices

如果你的主栈是 React / Next.js，这个几乎必装。

https://github.com/vercel-labs/agent-skills/tree/main/skills/react-best-practices…  
  
10\. figma-implement-design

对前端和产品协作非常实用，设计稿到代码的价值很直接。

https://github.com/openai/skills/tree/main/skills/.curated/figma-implement-design…

![Image](https://pbs.twimg.com/media/HEQv1LtacAAhopg?format=jpg&name=large)

---

**Colin Rong** @colinluckyrong [2026-03-26](https://x.com/colinluckyrong/status/2037126287765184652)

开发小哥哥小姐姐们看过来，这 Top10 Agent Skills 绝对是你们的菜！高效、实用，直接提升编码体验。mcp-builder 看着就让人兴奋，构建起来更得心应手了。别犹豫，码起来

---

**jaime** @jaimesolis [2026-03-25](https://x.com/jaimesolis/status/2036809615472472415)

本地验证和 ci 修复真的是核心，但工作流沉淀这块怎么落地？