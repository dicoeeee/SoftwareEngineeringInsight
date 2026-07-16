---
topic: software-development
recent_window_start: 2026-04-14
recent_window_end: 2026-07-13
generated_at: 2026-07-13T19:08:51+08:00
status: approved
approved_at: 2026-07-13
---

# 软件开发 Agent 基线摘要

## 当前格局（分析判断）

1. **入口从 IDE 聊天转向工作项与持久 Session。** Issue、Prompt、协作文档和定时事件正成为 Agent 入口，执行环境、验证产物和后续 PR 被组织在同一任务上下文中。
2. **架构从单 Agent 转向异步、多 Agent 与 Durable Execution。** Subagents、后台任务、执行状态持久化、失败恢复和跨机器调度成为 Cloud Agent 的基础能力。
3. **规范、计划与仓库知识成为一等工程工件。** Specs、Plan 文件、Steering/AGENTS 文件和可导航的工程知识用于控制 Agent，而不是只依赖一次性 Prompt。
4. **工具层从 Shell 深化到 IDE、浏览器和协作系统。** 语义索引、真实调试器、运行页面状态与外部工作项系统被直接接入 Agent。
5. **企业采用信号增多，但收益证据仍偏厂商自述。** 多仓库、安全与合规环境已有公开案例，量化收益仍需独立口径验证。

## 关键基线信号

| 信号 ID | 主分类 | 证据状态 | 事实、信号或主张摘要 | 主要来源 |
| --- | --- | --- | --- | --- |
| `sd-20260416-codex-persistent-partner` | 开发协作与工程知识上下文 | 已证实事实 | OpenAI 发布跨工具与跨时间任务能力 | [OpenAI](https://openai.com/index/codex-for-almost-everything/) |
| `sd-20260519-antigravity-multi-agent` | 开发协作与工程知识上下文 | 已证实事实 | Google 公布共享 Harness、异步任务与 Subagents | [Google](https://developers.googleblog.com/en/an-important-update-transitioning-gemini-cli-to-antigravity-cli/) |
| `sd-20260514-copilot-app-session` | 开发协作与工程知识上下文 | 早期信号 | 工作项、环境、验证与 PR 汇入 Agent Session | [GitHub](https://github.blog/changelog/2026-05-14-github-copilot-app-is-now-available-in-technical-preview/) |
| `sd-20260430-kiro-spec-driven` | 需求理解与任务规划 | 已证实事实 | AWS 宣布迁移至采用 Specs、Steering 和 Hooks 的 Kiro | [AWS](https://aws.amazon.com/blogs/devops/amazon-q-developer-end-of-support-announcement/) |
| `sd-20260617-junie-ide-runtime` | 本地调试与提交前验证 | 已证实事实 | Junie 可使用 Debug Session、IDE 语义和测试运行器 | [JetBrains](https://blog.jetbrains.com/junie/2026/06/junie-coding-agent-out-of-beta/) |
| `sd-20260602-cursor-durable-execution` | 开发协作与工程知识上下文 | 厂商主张 | 长任务可靠性依赖 Durable Execution | [Cursor](https://cursor.com/blog/cloud-agent-lessons) |
| `sd-20260625-cursor-sdk-notion` | 开发协作与工程知识上下文 | 厂商主张 | Agent Harness 通过 SDK 嵌入协作系统 | [Cursor](https://cursor.com/blog/notion) |
| `sd-20260616-openhands-agent-canvas` | 开发协作与工程知识上下文 | 已证实事实 | Agent Canvas 支持计划任务及 Slack、GitHub、Linear 事件 | [OpenHands](https://www.openhands.dev/blog/introducing-agent-canvas) |
| `sd-20260616-claude-code-expertise` | 需求理解与任务规划 | 已证实事实 | 使用数据表明人类承担更多规划决策；“Agent 放大执行”在信号记录中单列为分析 | [Anthropic](https://www.anthropic.com/research/claude-code-expertise) |
| `sd-20260527-cisco-codex-enterprise` | 编码与代码修改 | 厂商主张 | 联合案例称 Codex 用于 Cisco 多部门、多仓库研发流程 | [OpenAI/Cisco](https://openai.com/index/cisco/) |

## 仍然有效的历史材料

| 信号 ID | 发布时间 | 时效边界 | 来源 |
| --- | --- | --- | --- |
| `sd-20260401-copilot-research-plan` | 2026-04-01 | 支持“先研究/计划，再审批实施”的人机边界 | [GitHub](https://github.blog/changelog/2026-04-01-research-plan-and-code-with-copilot-cloud-agent/) |
| `sd-20260211-harness-engineering` | 2026-02-11 | 厂商内部实践，适合作为 Agent-ready 仓库参考 | [OpenAI](https://openai.com/index/harness-engineering/) |
| `sd-20260120-agent-readiness` | 2026-01-20 | 厂商框架，尚需跨厂商验证 | [Factory](https://factory.ai/news/agent-readiness) |

可演进的完整记录见 [基线信号库](./signals/baseline.md)。

## 待审核来源与检索词

- [P0/P1 候选来源](./sources.md)
- [基线检索词](./queries.md)
- [完整研究底稿](../../research/baseline-research.md)

## 覆盖缺口

- X、LinkedIn 登录态尚未完成可靠只读验证，短周期人物信号缺失。
- 视频、播客和会议转录未系统覆盖。
- 中文产品 TRAE、CodeBuddy、Comate、通义灵码/Qoder 等仍需逐条核验正式版本记录。
- 企业采用量和效率指标大多来自厂商或联合案例，缺少独立复核。
