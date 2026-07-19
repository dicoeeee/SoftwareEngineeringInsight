---
topic: software-development
baseline_window_start: 2026-04-14
baseline_window_end: 2026-07-13
discovered_at: 2026-07-13
status: approved
approved_at: 2026-07-13
signal_count: 13
---

# 软件开发 Agent 基线信号库

本文件保存基线初始化形成的可演进信号，不是历史日报。后续证据应追加到对应信号的支持来源与更新历史；未经人工审核不得把本文件或相关配置标为已批准。

## `sd-20260416-codex-persistent-partner` — Codex 扩展为跨工具、跨时间的开发伙伴

- 主分类：开发协作与工程知识上下文
- 横向标签：持久任务、浏览器、远程开发、Automation、Memory
- 自主程度：L3
- 证据状态：已证实事实
- 最高来源优先级：P1
- 相关性：高——直接改变开发 Agent 的执行边界
- 可信度：高——可追溯至官方产品发布
- 新颖性：高——从单次会话扩展到跨工具与跨时间任务
- 时效属性：current
- 事件/内容发布时间：2026-04-16
- 首次发现时间：2026-07-13
- 相关既有信号：无

### 信号

OpenAI 发布的 Codex 能力覆盖计算机操作、浏览器、SSH 远程开发、PR 审阅、多终端、Automation 与 Memory。

### 为什么重要

分析判断：Coding Agent 的产品边界开始从一次性终端会话扩展到可持续恢复的工程任务。

### 尚待确认

- 跨团队长期使用的稳定性、成本与收益尚缺独立证据。

### 支持来源

- P1 · [Codex for almost everything](https://openai.com/index/codex-for-almost-everything/) · OpenAI · 官方产品发布 · `2026-04-16`

### 更新历史

- `2026-07-13`：基线首次记录。

## `sd-20260519-antigravity-multi-agent` — Google 将 CLI 统一到异步多 Agent 平台

- 主分类：开发协作与工程知识上下文
- 横向标签：多 Agent、Subagents、Harness、后台任务
- 自主程度：L3
- 证据状态：已证实事实
- 最高来源优先级：P1
- 相关性：高——属于开发 Agent 的核心架构变化
- 可信度：高——两篇 Google 官方材料相互补充
- 新颖性：高——明确采用主 Agent 编排隔离 Subagents
- 时效属性：current
- 事件/内容发布时间：2026-05-19
- 首次发现时间：2026-07-13
- 相关既有信号：`sd-20260416-codex-persistent-partner`

### 信号

Google 将 Gemini CLI 与 Code Assist 的演进方向统一到 Antigravity CLI，并公开共享 Harness、异步后台任务、Subagents、Skills、Hooks 和 Extensions。

### 为什么重要

分析判断：主流开发 Agent 架构正从单 Agent、单上下文窗口转向隔离执行单元的编排。

### 尚待确认

- 迁移后的兼容性、可靠性与真实采用情况仍需实践材料验证。

### 支持来源

- P1 · [Transitioning Gemini CLI to Antigravity CLI](https://developers.googleblog.com/en/an-important-update-transitioning-gemini-cli-to-antigravity-cli/) · Google · 官方工程博客 · `2026-05-19`
- P1 · [Subagents in Gemini CLI](https://developers.googleblog.com/en/subagents-have-arrived-in-gemini-cli/) · Google · 官方工程博客 · `2026-05-19`

### 更新历史

- `2026-07-13`：基线首次记录。

## `sd-20260514-copilot-app-session` — 工作项、环境和验证汇入 Agent Session

- 主分类：开发协作与工程知识上下文
- 横向标签：工作项、隔离环境、浏览器验证、PR
- 自主程度：L3
- 证据状态：早期信号
- 最高来源优先级：P1
- 相关性：高——工作项成为开发 Agent 的新入口
- 可信度：中——官方技术预览，生产表现未验证
- 新颖性：高——把入口、环境、验证和变更组织为同一 Session
- 时效属性：current
- 事件/内容发布时间：2026-05-14
- 首次发现时间：2026-07-13
- 相关既有信号：`sd-20260416-codex-persistent-partner`

### 信号

GitHub Copilot App 技术预览支持从 Issue、PR、Prompt 或历史 Session 启动隔离开发任务，并在集成终端和浏览器中运行、预览和测试。

### 为什么重要

分析判断：开发入口正在从 IDE 聊天框迁移到以工作项为起点、携带执行环境和验证产物的 Agent Session。

### 尚待确认

- 技术预览的可用范围、稳定性与团队采用效果。
- PR、CI 与合并环节应继续由软件交付与运维专题跟踪。

### 支持来源

- P1 · [GitHub Copilot App technical preview](https://github.blog/changelog/2026-05-14-github-copilot-app-is-now-available-in-technical-preview/) · GitHub · 官方变更日志 · `2026-05-14`

### 更新历史

- `2026-07-13`：基线首次记录。

## `sd-20260430-kiro-spec-driven` — AWS 以 Spec-driven Agent 取代传统助手路线

- 主分类：需求理解与任务规划
- 横向标签：Spec-driven、Steering、Hooks、Global Hooks、Subagents、跨 Workspace
- 自主程度：L2
- 证据状态：已证实事实
- 最高来源优先级：P1
- 相关性：高——规范与规划属于开发 Agent 核心环节
- 可信度：高——AWS 官方迁移公告
- 新颖性：高——结构化 Spec 成为执行工件
- 时效属性：current
- 事件/内容发布时间：2026-04-30
- 首次发现时间：2026-07-13
- 相关既有信号：无

### 信号

AWS 宣布 Amazon Q Developer IDE 插件与付费订阅进入退场周期并引导迁移至 Kiro；Kiro 使用 Specs、Steering Files、Hooks 和自定义 Subagents 驱动实现。2026-07-17 的 Kiro CLI 2.13 / CLI 3.0 Early Access 又增加 Introspect Subagent，并允许 `~/.kiro/hooks/` 下的 Global Hooks 与 Workspace Hooks 并存、跨所有 Workspace 触发；官方示例包括保存时 Lint、提交前安全检查和自定义 Approval Gates。

### 为什么重要

分析判断：规范正从提示词附件变成 Agent 规划、实现和验证的工程工件。

### 尚待确认

- 迁移后的用户采用、跨语言效果与复杂项目成功率。
- Global Hooks 与 Workspace Hooks 的优先级、冲突处理、可见性和不可绕过性。

### 支持来源

- P1 · [Amazon Q Developer end-of-support announcement](https://aws.amazon.com/blogs/devops/amazon-q-developer-end-of-support-announcement/) · AWS · 官方公告 · `2026-04-30`
- P1 · [Introspect Subagent and Global Hooks](https://kiro.dev/changelog/cli/2-13/) · Kiro · 官方变更日志 · `2026-07-17`

### 更新历史

- `2026-07-13`：基线首次记录。
- `2026-07-18`：追加 Kiro CLI 2.13 / 3.0 Early Access 的 Introspect Subagent 与跨 Workspace Global Hooks；产品能力可确认，冲突与绕过行为仍待核验。

## `sd-20260617-junie-ide-runtime` — Junie 将真实调试器和 IDE 语义交给 Agent

- 主分类：本地调试与提交前验证
- 横向标签：IDE、Debugger、语义索引、Plan Mode
- 自主程度：L2
- 证据状态：已证实事实
- 最高来源优先级：P1
- 相关性：高——直接覆盖提交前调试与验证
- 可信度：高——JetBrains 官方 GA 发布
- 新颖性：高——Agent 工具层进入 IDE 运行时能力
- 时效属性：current
- 事件/内容发布时间：2026-06-17
- 首次发现时间：2026-07-13
- 相关既有信号：无

### 信号

Junie GA 的 Plan Mode 将计划保存为可编辑、可提交文档；Agent 可使用 IDE Debug Session、语义索引、测试运行器、构建配置和数据库连接。

### 为什么重要

分析判断：开发 Agent 的工具层正从 Shell 与文本搜索深化到 IDE 的语义和运行时能力。

### 尚待确认

- 真实项目中的调试成功率、性能开销与支持语言差异。

### 支持来源

- P1 · [Junie coding agent out of beta](https://blog.jetbrains.com/junie/2026/06/junie-coding-agent-out-of-beta/) · JetBrains · 官方产品博客 · `2026-06-17`

### 更新历史

- `2026-07-13`：基线首次记录。

## `sd-20260602-cursor-durable-execution` — Cloud Agent 需要 Durable Execution

- 主分类：开发协作与工程知识上下文
- 横向标签：Durable Execution、Temporal、状态恢复、重试
- 自主程度：L3
- 证据状态：厂商主张
- 最高来源优先级：P1
- 相关性：高——长任务可靠性是 Cloud Agent 核心约束
- 可信度：中——工程细节具体，但来自单一厂商自述
- 新颖性：高——公开了执行循环与会话状态解耦机制
- 时效属性：current
- 事件/内容发布时间：2026-06-02
- 首次发现时间：2026-07-13
- 相关既有信号：`sd-20260416-codex-persistent-partner`

### 信号

Cursor 称其 Cloud Agent 从 Work-stealing Loop 迁移到 Temporal，将 Agent Loop、机器状态和会话状态解耦，并以追加式会话流处理失败重试。

### 为什么重要

分析判断：Cloud Coding Agent 的壁垒包含环境恢复、状态持久化、重试语义和跨机器调度，而不只是模型能力。

### 尚待确认

- 厂商披露的可靠性和内部采用量缺少独立验证。

### 支持来源

- P1 · [Lessons from building cloud agents](https://cursor.com/blog/cloud-agent-lessons) · Cursor · 官方工程博客 · `2026-06-02`

### 更新历史

- `2026-07-13`：基线首次记录。

## `sd-20260625-cursor-sdk-notion` — Agent Harness 作为 SDK 嵌入协作系统

- 主分类：开发协作与工程知识上下文
- 横向标签：SDK、Notion、Slack、协作入口、Sandbox、多仓库、跨频道上下文
- 自主程度：L3
- 证据状态：厂商主张
- 最高来源优先级：P1
- 相关性：高——扩展了开发 Agent 的任务入口
- 可信度：中——联合案例来自供应商，缺少独立复核
- 新颖性：高——把协作 Thread 映射为 Agent Run
- 时效属性：current
- 事件/内容发布时间：2026-06-25
- 首次发现时间：2026-07-13
- 相关既有信号：`sd-20260514-copilot-app-session`

### 信号

Cursor 与 Notion 的联合案例称，Notion Thread 可映射为 Agent、Thread Message 映射为 Agent Run，由 Agent 规划、实现、测试、验证并开启 PR。2026-07-17 的官方 Changelog 进一步确认 Slack 入口会在执行前共享 Plan、执行中发布 Status；用户可启动命名的 Multi-repo Environment，当任务需要环境外仓库时必须显式点击 **Switch repository**，Agent 还可读取其他 Channel/Thread 的上下文并向其写入更新。

### 为什么重要

分析判断：业务系统可负责上下文与入口，专业 Harness 负责 Sandbox、模型路由和工具调用。

### 尚待确认

- 真实采用范围、失败率、权限治理与节省时间数据。
- 跨 Channel 读写的最小权限、审计方式，以及 Repository Switch 是否覆盖所有跨仓库工具路径。

### 支持来源

- P1 · [How Notion used Cursor's Agent SDK](https://cursor.com/blog/notion) · Cursor/Notion · 联合案例 · `2026-06-25`
- P1 · [Improvements to Cursor in Slack](https://cursor.com/changelog/slack-improvements) · Cursor · 官方变更日志 · `2026-07-17`

### 更新历史

- `2026-07-13`：基线首次记录。
- `2026-07-18`：追加 Slack Plan/Status、Multi-repo Environment、显式 Repository Switch 与跨频道读写控制面；能力可确认，权限隔离与可靠性待核验。

## `sd-20260616-openhands-agent-canvas` — 开源 Coding Agent 转向事件与定时工作流

- 主分类：开发协作与工程知识上下文
- 横向标签：开源、Scheduled、事件驱动、Agent Canvas、Portable JSON、StatefulSet、Per-commit Diff、Automation Timeout
- 自主程度：L3
- 证据状态：已证实事实
- 最高来源优先级：P1
- 相关性：高——开发 Agent 进入可调度工作流
- 可信度：高——官方发布且项目可公开检查
- 新颖性：高——从人工 Session 扩展到事件与计划任务
- 时效属性：current
- 事件/内容发布时间：2026-06-16
- 首次发现时间：2026-07-13
- 独立支持来源数：1
- 首次观察时间：2026-07-13
- 最近有效更新时间：2026-07-19T09:49:20+08:00
- 有效更新次数：3
- 关注度动量：持续
- 相关既有信号：`sd-20260416-codex-persistent-partner`

### 信号

OpenHands Agent Canvas 支持多种运行后端，并基于计划任务、Slack、GitHub 和 Linear 事件执行仓库摘要、Issue 清理、依赖检查、测试生成和文档漂移检查。2026-07-13/14 发布的 `v1.3.0` 与 `v1.4.0` 又支持把 Automations 导入/导出为 Portable JSON、导出 Markdown/HTML Transcript，并通过 StatefulSet Helm Chart 部署。`v1.5.0` 新增按 Commit 查看历史与 Diff、为每个 Automation 单独配置 Timeout、通过 `/launch` 以 Plugin 启动 Conversation，并支持 Subpath 部署与锁定 Cloud Canvas 的 Cookie Auth。

### 为什么重要

分析判断：开发 Agent 正从人工发起的 Session 转向可调度、可复用和可观察的工程流程。

### 尚待确认

- 不同后端的可靠性、安全边界和生产维护成本。
- Automation JSON 的兼容性、秘密信息处理和版本迁移，以及 StatefulSet 部署的升级与恢复行为。
- Per-automation Timeout 的终止、取消、恢复与重试语义，以及 Commit View 是否能覆盖跨 Branch、Squash 和未提交变更。

### 支持来源

- P1 · [Introducing Agent Canvas](https://www.openhands.dev/blog/introducing-agent-canvas) · OpenHands · 官方项目博客 · `2026-06-16`
- P1 · [Agent Canvas v1.3.0](https://github.com/OpenHands/agent-canvas/releases/tag/v1.3.0) · OpenHands · GitHub Release · `2026-07-13`
- P1 · [Agent Canvas v1.4.0](https://github.com/OpenHands/agent-canvas/releases/tag/v1.4.0) · OpenHands · GitHub Release · `2026-07-14`
- P1 · [Agent Canvas v1.5.0](https://github.com/OpenHands/agent-canvas/releases/tag/v1.5.0) · OpenHands · GitHub Release · `2026-07-17`

### 更新历史

- `2026-07-13`：基线首次记录。
- `2026-07-18`：追加 Automation Portable JSON、Transcript 导出与 StatefulSet Helm 部署，说明可调度工作流开始获得可移植和自托管能力。
- `2026-07-19`：追加 Per-commit Diff 与 Per-automation Timeout；既有信号继续获得可审查性和运行时边界证据，关注度动量记为“持续”。

## `sd-20260616-claude-code-expertise` — 人类承担更多规划决策

- 主分类：需求理解与任务规划
- 横向标签：人机分工、使用研究、规划、执行
- 自主程度：L2
- 证据状态：已证实事实
- 最高来源优先级：P1
- 相关性：高——直接说明当前开发 Agent 的人机边界
- 可信度：高——大样本隐私保护使用研究，但仍受产品样本限制
- 新颖性：中——为既有分工判断增加实证
- 时效属性：current
- 事件/内容发布时间：2026-06-16
- 首次发现时间：2026-07-13
- 相关既有信号：无

### 信号

Anthropic 对 Claude Code Session 的分析显示，典型 Session 中人类承担更多规划决策，Claude 承担更多执行决策；领域知识与单次指令可完成工作量、成功率相关。

### 为什么重要

分析判断：当前开发 Agent 更像执行杠杆，而不是需求判断的替代品；上下文、验收条件和错误恢复仍是关键。

### 尚待确认

- 研究结论在其他开发 Agent、组织类型和长期项目中能否复现。

### 支持来源

- P1 · [Claude Code and expertise](https://www.anthropic.com/research/claude-code-expertise) · Anthropic · 官方研究 · `2026-06-16`

### 更新历史

- `2026-07-13`：基线首次记录；事实与分析判断分段表达。

## `sd-20260527-cisco-codex-enterprise` — Coding Agent 进入大型多仓库企业流程

- 主分类：编码与代码修改
- 横向标签：企业采用、多仓库、治理、C/C++
- 自主程度：待核验
- 证据状态：厂商主张
- 最高来源优先级：P1
- 相关性：高——反映企业研发流程采用
- 可信度：中——联合案例具体但缺少独立口径
- 新颖性：中——补充多仓库与合规环境案例
- 时效属性：current
- 事件/内容发布时间：2026-05-27
- 首次发现时间：2026-07-13
- 相关既有信号：无

### 信号

OpenAI 与 Cisco 联合案例称，Cisco 在多业务部门、多仓库、C/C++、安全与合规环境中使用 Codex，并披露吞吐与节省工程时间等数据。

### 为什么重要

分析判断：Coding Agent 正从个人工具扩展到受治理的企业工程基础设施。

### 尚待确认

- 采用范围和收益数字需要独立口径验证。

### 支持来源

- P1 · [Cisco scales an AI-powered engineering workforce with Codex](https://openai.com/index/cisco/) · OpenAI/Cisco · 联合客户案例 · `2026-05-27`

### 更新历史

- `2026-07-13`：基线首次记录。

## `sd-20260401-copilot-research-plan` — Cloud Agent 支持先研究和计划再实施

- 主分类：需求理解与任务规划
- 横向标签：Research、Plan、审批、人机边界
- 自主程度：L2
- 证据状态：已证实事实
- 最高来源优先级：P1
- 相关性：高——覆盖任务规划和实施审批
- 可信度：高——官方变更日志
- 新颖性：中——作为人机边界的历史参照
- 时效属性：historical
- 事件/内容发布时间：2026-04-01
- 首次发现时间：2026-07-13
- 相关既有信号：`sd-20260430-kiro-spec-driven`

### 信号

GitHub Copilot Cloud Agent 可先生成实施计划供批准，在分支上迭代而不立即创建 PR，并基于仓库上下文进行研究。

### 为什么重要

分析判断：该材料仍可作为“先研究和计划，再批准实施”的人机控制边界参考。

### 尚待确认

- 后续版本是否改变交互与审批机制。

### 支持来源

- P1 · [Research, plan, and code with Copilot cloud agent](https://github.blog/changelog/2026-04-01-research-plan-and-code-with-copilot-cloud-agent/) · GitHub · 官方变更日志 · `2026-04-01`

### 更新历史

- `2026-07-13`：历史补录。

## `sd-20260211-harness-engineering` — Agent-first 团队重视环境与反馈回路

- 主分类：开发协作与工程知识上下文
- 横向标签：Agent-ready、仓库知识、反馈回路
- 自主程度：待核验
- 证据状态：厂商主张
- 最高来源优先级：P1
- 相关性：高——直接涉及 Agent-ready 工程环境
- 可信度：中——厂商内部实践，缺少外部复现
- 新颖性：中——形成仓库可导航性与反馈回路框架
- 时效属性：historical
- 事件/内容发布时间：2026-02-11
- 首次发现时间：2026-07-13
- 相关既有信号：无

### 信号

OpenAI 的 Harness Engineering 实践强调设计 Agent 可导航的仓库、明确意图、构建确定性反馈回路，并让业务知识在仓库内可发现。

### 为什么重要

分析判断：Agent-first 团队的主要工程对象开始包含执行环境和反馈机制，而不仅是提示词。

### 尚待确认

- 该方法在其他组织、技术栈与规模下的复现效果。

### 支持来源

- P1 · [Harness engineering](https://openai.com/index/harness-engineering/) · OpenAI · 官方工程实践 · `2026-02-11`

### 更新历史

- `2026-07-13`：历史补录。

## `sd-20260120-agent-readiness` — 代码库是否适合 Agent 成为评估对象

- 主分类：开发协作与工程知识上下文
- 横向标签：Agent Readiness、测试反馈、环境配置
- 自主程度：待核验
- 证据状态：厂商主张
- 最高来源优先级：P1
- 相关性：高——关注开发 Agent 的落地条件
- 可信度：中——供应商框架，尚无跨厂商验证
- 新颖性：中——把仓库适配度显式化为评估对象
- 时效属性：historical
- 事件/内容发布时间：2026-01-20
- 首次发现时间：2026-07-13
- 相关既有信号：`sd-20260211-harness-engineering`

### 信号

Factory 的 Agent Readiness 框架从多个技术维度评估仓库，并把快速测试、环境配置和提交前反馈列为 Agent 效果约束。

### 为什么重要

分析判断：组织需要把代码库和反馈系统对 Agent 的适配度作为独立治理对象。

### 尚待确认

- 框架指标与真实任务成功率的关联，以及跨工具通用性。

### 支持来源

- P1 · [Agent Readiness](https://factory.ai/news/agent-readiness) · Factory · 官方框架 · `2026-01-20`

### 更新历史

- `2026-07-13`：历史补录。
