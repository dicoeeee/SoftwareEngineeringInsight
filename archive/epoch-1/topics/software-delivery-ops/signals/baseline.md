---
topic: software-delivery-ops
baseline_window_start: 2026-04-14
baseline_window_end: 2026-07-13
discovered_at: 2026-07-13
status: approved
approved_at: 2026-07-13
signal_count: 10
---

# 软件交付与运维 Agent 基线信号库

本文件保存基线初始化形成的可演进信号，不是历史日报。后续证据应追加到对应信号的支持来源与更新历史；未经人工审核不得把本文件或相关配置标为已批准。

## `sdo-20260416-gitlab-agent-control-plane` — GitLab 推进事件驱动 DevSecOps Agent 控制面

- 主分类：变更接入、代码评审与合并准入
- 横向标签：CI/CD Agent、事件驱动、权限、审计、DevSecOps
- 自主程度：L3
- 证据状态：已证实事实
- 最高来源优先级：P1
- 相关性：高——从 MR 和流水线事件进入交付控制面
- 可信度：高——连续官方版本材料可追溯
- 新颖性：高——权限与审计从 Prompt 约束升级到平台机制
- 时效属性：current
- 事件/内容发布时间：2026-04-16 至 2026-07-16
- 首次发现时间：2026-07-13
- 相关既有信号：无

### 信号

GitLab 18.11–19.1 将漏洞修复、Developer Flow、MR/流水线事件触发、工具 Allow/Ask/Deny、模型白名单和审计事件逐步整合到平台；其中个别功能仍为 Beta。

`2026-07-17` 更新：GitLab 19.2 把多条 Agentic Flow 推进到 MR 与流水线控制面。Security Review Flow Public Beta 会结合 diff、原始代码、MR 讨论与相关代码进行两阶段安全审查，并按严重度选择 `Request changes` 或评论、且不自动批准；Fix CI/CD Pipeline Flow 已 GA，可读取日志、MR 变更和脚本错误，在 diff 内直接建议、在 diff 外另建 MR，信息不足或安全敏感时只评论。Dependency Auto-Remediation Beta 可从依赖扫描结果创建服务账号 MR，并在流水线失败后继续迭代；Custom Flows GA 支持事件触发、复合身份和 Human-in-the-loop 检查点。以上为官方材料可确认的能力与行为契约，不证明审查准确率或自动修复效果。

### 为什么重要

分析判断：Agent 正从人工调用的单点功能转向事件驱动的 DevSecOps 控制面。

`2026-07-17` 分析判断：19.2 将“发现问题—生成变更—流水线反馈—继续迭代—人工准入”进一步收敛到 MR 状态机；同时，以不自动批准、风险分级、复合身份和检查点约束 Agent，说明平台控制面正在把自主执行与合并权分离。

### 尚待确认

- Beta 能力的稳定性、企业采用范围和治理成本。
- Security Review 的误报/漏报、Dependency Auto-Remediation 的成功率，以及服务账号 MR 的权限与回滚边界。
- Fix Pipeline 当前只读取最后 150 KiB 日志，沙箱有时不能验证依赖安装，且不保证遵循 `AGENTS.md`；这些限制在真实仓库中的影响仍待评估。

### 支持来源

- P1 · [GitLab 18.11](https://about.gitlab.com/whats-new/18-11/) · GitLab · 官方版本说明 · `2026-04-16`
- P1 · [GitLab 19.0](https://about.gitlab.com/whats-new/19-0/) · GitLab · 官方版本说明 · `2026-05`
- P1 · [GitLab 19.1](https://about.gitlab.com/whats-new/19-1/) · GitLab · 官方版本说明 · `2026-06-18`
- P1 · [GitLab Duo Security Review Flow](https://about.gitlab.com/blog/gitlab-duo-security-review-flow/) · GitLab · 官方产品博客 · `2026-07-16`
- P1 · [Fix CI/CD Pipeline Flow](https://docs.gitlab.com/user/duo_agent_platform/flows/foundational_flows/fix_pipeline/) · GitLab · 官方文档 · `2026-07-17`（本轮核验）
- P1 · [Dependency scanning auto-remediation](https://about.gitlab.com/blog/dependency-scanning-auto-remediation/) · GitLab · 官方产品博客 · `2026-07-16`
- P1 · [Multi-step software delivery with agentic flows](https://about.gitlab.com/blog/multi-step-software-delivery-with-agentic-flows/) · GitLab · 官方产品博客 · `2026-07-16`

### 更新历史

- `2026-07-13`：基线首次记录。
- `2026-07-17`：追加 GitLab 19.2 的 Security Review、Fix Pipeline、Dependency Auto-Remediation 与 Custom Flows；区分 GA/Public Beta 和产品行为事实与效果证据，主证据状态维持“已证实事实”。

## `sdo-20260422-gemini-cloud-assist-ops` — Gemini Cloud Assist 承担持续云运维与 FinOps

- 主分类：云、Kubernetes 与平台运维
- 横向标签：AIOps、FinOps、告警调查、MCP
- 自主程度：L3
- 证据状态：已证实事实
- 最高来源优先级：P1
- 相关性：高——覆盖常态云运维、Kubernetes 与成本治理
- 可信度：高——能力可追溯到官方发布；效果数字不计入事实
- 新颖性：高——运维与 FinOps 共享持续 Agent 上下文
- 时效属性：current
- 事件/内容发布时间：2026-04-22
- 首次发现时间：2026-07-13
- 相关既有信号：无

### 信号

Google 发布的 Gemini Cloud Assist 可由告警发起调查、并行验证假设，并通过 `gcloud`、`kubectl` 和 Terraform 执行云运维；后台 FinOps Agent 持续检测成本异常并关联资源变更。

### 为什么重要

分析判断：部署、故障调查和成本优化开始共享同一 Agent 上下文，并通过 MCP 向开发与协作工具开放。

### 尚待确认

- 厂商公布的效果数字、生产可靠性与人工介入比例需要独立验证。

### 支持来源

- P1 · [Gemini Cloud Assist at Next '26](https://cloud.google.com/blog/products/application-development/gemini-cloud-assist-at-next26) · Google Cloud · 官方产品博客 · `2026-04-22`

### 更新历史

- `2026-07-13`：基线首次记录；效果数字未并入事实状态。

## `sdo-20260602-github-review-actions` — 内部上下文进入评审并闭环 Actions 修复

- 记录状态：active
- 主分类：变更接入、代码评审与合并准入
- 横向标签：CI/CD Agent、Code Review、GitHub Actions、AGENTS.md
- 自主程度：L3
- 证据状态：已证实事实
- 最高来源优先级：P1
- 相关性：高——覆盖 PR 评审、合并前上下文和 CI 修复
- 可信度：高——多条官方变更日志相互补充
- 新颖性：高——评审依据扩展到内部规范与工具
- 时效属性：current
- 事件/内容发布时间：2026-06-02 至 2026-07-17
- 首次发现时间：2026-07-13
- 独立支持来源数：1
- 首次观察时间：2026-07-13
- 最近有效更新时间：2026-07-18T11:13:38+08:00
- 有效更新次数：2
- 关注度动量：持续
- 相关既有信号：`sdo-20260416-gitlab-agent-control-plane`

### 信号

Copilot code review 支持 Agent Skills、MCP、`AGENTS.md`、组织级 runner 和内容排除；GitHub Actions 失败可调用 cloud agent 调查、修改分支并请求人工复核，部分能力仍为 Public Preview。

`2026-07-18` 更新：Copilot code review 改为从 PR head branch 读取 `copilot-instructions.md`、`*.instructions.md`、Agent Skills 与 `AGENTS.md`，并新增 `REVIEW.md`、`GEMINI.md`、`CLAUDE.md`；仓库可用 `.github/workflows/copilot-code-review.yml` 配置 setup steps 与独立 runner。评审默认运行在可独立配置的 firewall 后，但 self-hosted runner 当前不支持该 firewall；code review 与 cloud agent 的组织级 runner 配置也已分离。以上为官方变更日志可确认的行为与限制。

### 为什么重要

分析判断：评审依据从 diff 扩展到内部规范与工具，流水线修复也从建议进入可审查变更。

`2026-07-18` 分析判断：head-branch 指令让团队能在合并前验证评审规则，但也意味着待审分支可以影响审查 Agent 的上下文；默认 firewall 与独立 runner 配置提供了运行边界，而 self-hosted runner 无 firewall 是必须显式保留的部署差异。

### 尚待确认

- 评审准确率、CI 修复成功率和组织级安全边界。
- head-branch 指令与自定义 setup steps 面对恶意 PR 时的信任模型、允许动作和审核责任。
- self-hosted runner 缺少 firewall 时的网络、凭据和依赖安装隔离，以及未来支持时间。

### 支持来源

- P1 · [Skills/MCP for code review](https://github.blog/changelog/2026-06-02-shape-copilot-code-review-around-your-team/) · GitHub · 官方变更日志 · `2026-06-02`
- P1 · [Fix failing Actions with Copilot](https://github.blog/changelog/2026-06-04-fix-with-copilot-for-failing-actions-now-in-pro-pro-and-max/) · GitHub · 官方变更日志 · `2026-06-04`
- P1 · [`AGENTS.md` support](https://github.blog/changelog/2026-06-18-copilot-code-review-agents-md-support-and-ui-improvements/) · GitHub · 官方变更日志 · `2026-06-18`
- P1 · [Copilot code review: Customization and configurability improvements](https://github.blog/changelog/2026-07-17-copilot-code-review-customization-and-configurability-improvements/) · GitHub · 官方变更日志 · `2026-07-17`

### 更新历史

- `2026-07-13`：基线首次记录。
- `2026-07-18`：追加 head-branch 指令、自定义 setup、默认 firewall、独立 runner 配置及 self-hosted runner 无 firewall 的限制；维持“已证实事实”。

## `sdo-20260609-datadog-release-loop` — 生产遥测闭环到代码修复与发布验证

- 主分类：可观测与上线后校验
- 横向标签：CI/CD Agent、SRE、Release Verification、生产遥测
- 自主程度：L3
- 证据状态：早期信号
- 最高来源优先级：P1
- 相关性：高——直接连接上线后数据、修复和再发布
- 可信度：中——官方预览材料，生产成效未验证
- 新颖性：高——描述了从生产信号到发布验证的完整闭环
- 时效属性：current
- 事件/内容发布时间：2026-06-09
- 首次发现时间：2026-07-13
- 相关既有信号：无

### 信号

Datadog 将错误、性能回归、测试、漏洞、数据库和 Kubernetes 问题连接到代码修复，并让 Bits Release 从 PR 制定验证计划、在 staging 检查并监控生产发布；Bits Code 已 GA，Bits Release 等仍为 Preview。

### 为什么重要

分析判断：同一平台开始覆盖“生产遥测—根因—代码修复—PR—发布验证—生产监控”闭环。

### 尚待确认

- Preview 能力的自主程度、准确率、MTTR 影响和误操作防护。

### 支持来源

- P1 · [Datadog DASH 2026 roundup](https://www.datadoghq.com/blog/dash-2026-new-feature-roundup-keynote/) · Datadog · 官方产品发布 · `2026-06-09`

### 更新历史

- `2026-07-13`：基线首次记录。

## `sdo-20260617-aws-release-management` — AWS DevOps Agent 扩展到发布就绪评审

- 主分类：发布与渐进式交付
- 横向标签：CI/CD Agent、Release Readiness、风险评估、测试
- 自主程度：L3
- 证据状态：早期信号
- 最高来源优先级：P1
- 相关性：高——覆盖 PR 到生产前评估和测试
- 可信度：中——官方 Preview，缺少生产复现
- 新颖性：高——同一 Agent 连接代码、流水线、拓扑与生产风险
- 时效属性：current
- 事件/内容发布时间：2026-06-17
- 首次发现时间：2026-07-13
- 相关既有信号：无

### 信号

AWS DevOps Agent Preview 建立代码与云资源依赖图，对 PR/MR 执行风险、依赖、安全和组织标准检查，并在生产相似环境生成和执行变更专属测试。

### 为什么重要

分析判断：软件交付与运维的上下文边界正在融合。

### 尚待确认

- Preview 的安全性、支持范围、BLOCK/Proceed/Safe 决策准确率与真实生产成效。

### 支持来源

- P1 · [AWS DevOps Agent release management](https://aws.amazon.com/blogs/aws/aws-devops-agent-adds-release-management-capabilities-to-assess-code-changes-before-production-preview/) · AWS · 官方发布 · `2026-06-17`
- P1 · [What's new](https://docs.aws.amazon.com/devopsagent/latest/userguide/whats-new.html) · AWS · 官方文档 · `2026-06-17`

### 更新历史

- `2026-07-13`：基线首次记录。

## `sdo-20260630-harness-worker-agents` — Agent 进入既有流水线治理控制面

- 主分类：流水线编排与调度
- 横向标签：CI/CD Agent、RBAC、OPA、Kubernetes、短期凭据
- 自主程度：L3
- 证据状态：已证实事实
- 最高来源优先级：P1
- 相关性：高——Agent 直接作为受治理的流水线步骤
- 可信度：高——架构与安全机制来自官方材料；客户收益不计入事实
- 新颖性：高——复用既有交付治理约束 Agent
- 时效属性：current
- 事件/内容发布时间：2026-06-30 至 2026-07-16
- 首次发现时间：2026-07-13
- 相关既有信号：`sdo-20260416-gitlab-agent-control-plane`

### 信号

Harness Autonomous Worker Agents 可作为 pipeline step 运行，继承 RBAC、OPA、审批门、审计和成本跟踪，并在客户 Kubernetes/VPC 中使用非 root、只读文件系统和短期凭据执行。

`2026-07-15` 更新（厂商主张）：Harness 进一步把 Agent 已获得 RCE 作为威胁模型，描述了 hardened image、同容器三用户隔离、secret broker 与 egress proxy 四层确定性控制；真实秘密由目标绑定、单次使用的 placeholder 与短期凭据替代，出站访问受 allowlist、kernel firewall pinning 和响应凭据 scrub 约束。文章自述的 CVSS 9.0 攻击链、`709→33` 环境变量收敛和 `0/8` callback 绕过结果尚无独立复现，不并入本信号的事实状态。

`2026-07-16` 更新：Harness 进一步公开身份与权限模型。Agent 以触发者身份运行，每次 run 使用权限为“Agent 声明范围 ∩ 触发者 RBAC”的 scoped ephemeral token；author、publish、execute 与 connector use 分为专用 RBAC 权限，OPA 在 save/trigger 阶段约束 Agent 定义。MCP gateway 对每次调用执行 `connector.allowedTools ∩ agent.allowedTools`，并记录 agent、run、principal、tool、parameters 与 result，实现逐调用归因。以上为官方材料可确认的产品控制语义；安全效果仍缺独立验证。

### 为什么重要

分析判断：Agent 的安全边界可以由现有交付基础设施强制执行，而不是只依赖提示词。

`2026-07-15` 分析判断：安全边界进一步下沉到凭据代理、出站网络和镜像发布门禁，说明 L3 受控执行需要把 Agent 进程按已失陷组件对待。

`2026-07-16` 分析判断：隔离之外，L3 执行还需要把触发者身份、声明范围、平台 RBAC、OPA 与工具 allowlist 取交集，并让所有检查在服务端逐层失败关闭。

### 尚待确认

- 客户收益、运行规模和故障率属于厂商主张，尚缺独立验证。
- 客户自托管 runner 是否获得相同的 kernel firewall、egress 和 secret broker 强制能力。
- 内部红队结果、secret scrub 的误报/漏报、性能开销和多租户隔离仍待独立验证。
- 临时 token 的撤销、长任务续租、重试/子 Agent 权限传播和跨账户执行语义未公开。
- 参数与结果审计对秘密、PII 和高体量输出的脱敏、保留与查询边界仍待核验。

### 支持来源

- P1 · [Autonomous Worker Agents](https://www.harness.io/blog/introducing-autonomous-worker-agents) · Harness · 官方产品博客 · `2026-06-30`
- P1 · [How We Secured AI Worker Agents in Harness](https://www.harness.io/blog/how-we-secured-ai-worker-agents-in-harness) · Harness · 官方工程文章 · `2026-07-13`
- P1 · [Identity and Permissions for AI Worker Agents in Harness](https://www.harness.io/blog/identity-and-permissions-for-ai-worker-agents-in-harness) · Harness · 官方工程文章 · `2026-07-16`
- P1 · [Worker Agent permissions](https://developer.harness.io/docs/platform/harness-ai/core-capabilities/in-your-pipelines/permissions/) · Harness · 官方权限文档 · `2026-07-16`（本轮核验）

### 更新历史

- `2026-07-13`：基线首次记录；客户收益未并入事实状态。
- `2026-07-15`：追加四层确定性隔离、凭据代理、出站控制和发布门禁的厂商工程说明；内部红队数字维持“厂商主张”，主证据状态不变。
- `2026-07-16`：追加触发者身份、每次运行临时 token、权限交集、OPA save/trigger 检查、MCP 工具交集授权与逐调用归因；主证据状态维持“已证实事实”。

## `sdo-20260601-pagerduty-parallel-investigation` — 事故调查转向并行假设 Agent

- 主分类：故障诊断、事件响应与自动修复
- 横向标签：SRE Agent、并行假设、Coordinator、Human-in-the-loop
- 自主程度：L3
- 证据状态：已证实事实
- 最高来源优先级：P1
- 相关性：高——属于生产事故调查核心架构
- 可信度：高——官方工程复盘与产品状态可追溯
- 新颖性：高——公开从单 Agent 到并行调查架构的原因
- 时效属性：current
- 事件/内容发布时间：2026-06-01 至 2026-07-13
- 首次发现时间：2026-07-13
- 相关既有信号：无

### 信号

PagerDuty 说明单 Agent 在真实事故调查中遇到 context rot、指令过载、串行延迟和不可中途干预，随后改为协调器并行派生多个假设调查 Agent，并支持实时进度、人工注入和取消。

`2026-07-16` 更新：PagerDuty 的 Event Enrichment Early Access 可从 CMDB、developer tools 与 CSV files 自动拉取事件上下文，提供 account-level defaults、service-specific overrides 与 team-based access，并明确用于向 SRE Agent 提供环境视图。该材料补充的是既有 SRE Agent 的受控上下文入口，不代表新的调查架构或效果验证。

### 为什么重要

分析判断：生产级 SRE Agent 需要并行假设、可观察进度和人工可控性。

`2026-07-16` 分析判断：并行调查之外，SRE Agent 还需要有默认值、服务覆盖和团队权限约束的上下文供给层，避免把所有环境数据无差别暴露给调查流程。

### 尚待确认

- 对 MTTR、误诊率和工程师负担的独立量化影响。
- Event Enrichment 的数据新鲜度、冲突解决、来源可信度与对调查质量的实际影响未披露。

### 支持来源

- P1 · [Inside PagerDuty's SRE Agent](https://www.pagerduty.com/eng/inside-pagerdutys-sre-agent-how-we-built-deep-incident-investigation/) · PagerDuty · 官方工程博客 · `2026-06-01`
- P1 · [AI Orchestrations GA](https://support.pagerduty.com/main/changelog/ai-orchestrations-now-generally-available) · PagerDuty · 官方变更日志 · `2026-06`
- P1 · [Event Enrichment now available for Early Access](https://support.pagerduty.com/main/changelog/event-enrichment-now-available-for-early-access) · PagerDuty · 官方变更日志 · `2026-07-13`

### 更新历史

- `2026-07-13`：基线首次记录。
- `2026-07-16`：补齐上轮不可达的 Event Enrichment 正文，追加受团队权限约束的 CMDB、开发工具和 CSV 上下文入口；维持“已证实事实”的既有主状态，新增 EA 能力单独保留“早期信号”边界。

## `sdo-20260609-google-secops-agents` — 动态 Agent 与确定性 Playbook 分层

- 主分类：安全运营
- 横向标签：SecOps、Playbook、确定性执行、Human-in-the-loop
- 自主程度：L3
- 证据状态：已证实事实
- 最高来源优先级：P1
- 相关性：高——覆盖高风险安全运营的人机控制
- 可信度：高——官方产品材料；效果数字不计入事实
- 新颖性：高——明确区分自主调查与确定性处置
- 时效属性：current
- 事件/内容发布时间：2026-06-09
- 首次发现时间：2026-07-13
- 相关既有信号：无

### 信号

Google Security Operations 的调查 Agent 负责收集证据与推理，高风险处置仍由确定性企业 Playbook 与人工控制；部分 Agent 已 GA，部分为 Preview。

`2026-07-15` 更新：Google SecOps 官方文档补充了 GA autonomous agents 的资源准入语义——Security Tokens 按 tenant 单独启用和计量，每个 GA Agent 有内建 consumption limits 以抑制 runaway logic loops 或误配置，管理员可设置每日 paid-token ceiling；额度耗尽后拒绝新的 Agent 启动，但允许已经运行的 Agent 完成。Preview Agent 与辅助摘要当前不消耗 Security Tokens。

### 为什么重要

分析判断：这是“自主推理、确定性执行”分层的清晰安全模型。

`2026-07-15` 分析判断：Agent 治理从操作权限扩展到成本、循环上限和启动准入，且“拒绝新启动、允许在途完成”形成了明确的资源耗尽语义。

### 尚待确认

- 厂商效果数字、真实误报率和大规模生产运行表现。
- 每个 Agent 的内建上限、计算方法和额度耗尽时的在途任务中止能力未公开。

### 支持来源

- P1 · [Google Security Operations agents](https://cloud.google.com/blog/products/identity-security/detecting-and-containing-powered-threats-with-google-security-operations-agents) · Google Cloud · 官方产品博客 · `2026-06-09`
- P1 · [Google SecOps Agentic SOC Security Tokens pricing and billing](https://docs.cloud.google.com/chronicle/docs/agentic-soc/security-tokens) · Google Cloud · 官方产品文档 · `2026-07-13`（页面更新时间）

### 更新历史

- `2026-07-13`：基线首次记录；效果数字未并入事实状态。
- `2026-07-15`：追加按 tenant 计量、内建循环限制、每日额度上限和启动准入语义；维持“已证实事实”。

## `sdo-20260615-multicloud-sre-orchestration` — 多云 SRE 转向专业 Agent 编排

- 主分类：云、Kubernetes 与平台运维
- 横向标签：Multi-cloud、Kubernetes、知识图谱、Agent Orchestration
- 自主程度：L3
- 证据状态：分析判断
- 最高来源优先级：P1
- 相关性：高——描述复杂常态运维的架构方向
- 可信度：中——由两个厂商架构案例归纳，缺少独立采用证据
- 新颖性：高——出现跨云与领域专业 Agent 的共同结构
- 时效属性：current
- 事件/内容发布时间：2026-06-15 至 2026-06-24
- 首次发现时间：2026-07-13
- 相关既有信号：`sdo-20260601-pagerduty-parallel-investigation`

### 信号

分析判断：结合 Dynatrace 编排多云运维 Agent 与 Komodor 的 Kubernetes 协调器、领域 Agent、知识图谱及防护层，可见复杂运维正在形成“协调器 + 专业 Agent + 拓扑/知识图谱 + 统一审计”的共同结构。

### 为什么重要

该结构比单个模型连接所有工具更适合隔离权限、并行调查与领域验证，值得作为持续观察假设。

### 尚待确认

- 两家厂商的采用量、效果数字和跨平台互操作性均需独立验证。

### 支持来源

- P1 · [Dynatrace Cloud SRE Agents](https://www.dynatrace.com/news/blog/orchestrate-multicloud-ai-agents-for-autonomous-incident-resolution/) · Dynatrace · 官方产品博客 · `2026-06-15`
- P1 · [Komodor multi-agent AI SRE](https://komodor.com/blog/multi-agent-ai-sre-has-landed-and-its-built-for-your-most-complex-stacks/) · Komodor · 官方工程博客 · `2026-06-24`

### 更新历史

- `2026-07-13`：基线首次记录；状态为跨来源分析判断。

## `sdo-20260603-alibaba-agentic-ops` — 国内 Agentic Ops 公开架构与 RCA 评测

- 主分类：安全运营
- 横向标签：Agentic Ops、RCA Benchmark、Quality Gate、国内实践
- 自主程度：待核验
- 证据状态：早期信号
- 最高来源优先级：P1
- 相关性：高——覆盖 SecOps 与生产根因分析
- 可信度：中——官方材料与公开基准，外部复现仍不足
- 新颖性：高——国内公开可复现 RCA 评测框架
- 时效属性：current
- 事件/内容发布时间：2026-06-03 至 2026-06-15
- 首次发现时间：2026-07-13
- 相关既有信号：无

### 信号

阿里云公开 Agentic SOC 多 Agent 架构，并发布分布式系统故障诊断的 RCA Benchmark、评分协议与 Quality Gate。

### 为什么重要

分析判断：可复现 RCA 评测比运维聊天界面更有助于验证 Agent 是否真正能够诊断生产故障。

### 尚待确认

- 基准的外部复现、题目代表性与对真实生产 MTTR 的预测力。

### 支持来源

- P1 · [Agentic SOC architecture](https://www.alibabacloud.com/help/en/security-center/user-guide/agentic-soc-agent-architecture) · Alibaba Cloud · 官方文档 · `2026-06-03`
- P1 · [RCA Benchmark](https://www.alibabacloud.com/blog/alibaba-cloud-releases-rca-benchmark-the-industrys-first-open-source-root-cause-analysis-benchmark-system-for-agentic-ops_603252) · Alibaba Cloud · 官方技术博客 · `2026-06-15`

### 更新历史

- `2026-07-13`：基线首次记录。
