---
topic: software-delivery-ops
recent_window_start: 2026-04-14
recent_window_end: 2026-07-13
generated_at: 2026-07-13T19:08:51+08:00
status: approved
approved_at: 2026-07-13
---

# 软件交付与运维 Agent 基线摘要

## 当前格局（分析判断）

1. **Agent 正从单点功能变成交付事件驱动的控制面。** MR、流水线失败、告警和安全事件开始自动触发 Agent，身份、工具权限和审计逐步平台化。
2. **代码、流水线、拓扑与生产遥测开始进入同一上下文。** PR 风险评估、变更专属测试、发布验证、生产监控和代码修复正在形成闭环。
3. **治理更依赖既有交付基础设施。** RBAC、OPA、审批门、短期凭据、只读文件系统和确定性 Playbook 用于约束 Agent，而不是只依赖 Prompt。
4. **复杂事故调查转向协调器与专业 Agent。** 并行假设、知识图谱、领域 Agent、统一审计和人工可中断成为生产 SRE Agent 的共同设计。
5. **产品发布多于独立效果证据。** 多数自主性、MTTR、采用量和成本收益仍来自厂商主张，需要继续寻找客户工程材料与可复现评测。

## 关键基线信号

| 信号 ID | 主分类 | 证据状态 | 事实、信号或主张摘要 | 主要来源 |
| --- | --- | --- | --- | --- |
| `sdo-20260416-gitlab-agent-control-plane` | 变更接入、代码评审与合并准入 | 已证实事实 | GitLab 发布 MR/流水线事件触发、工具权限与审计能力 | [GitLab](https://about.gitlab.com/whats-new/19-1/) |
| `sdo-20260422-gemini-cloud-assist-ops` | 云、Kubernetes 与平台运维 | 已证实事实 | Cloud Assist 支持告警调查、云工具调用和持续 FinOps 检测 | [Google Cloud](https://cloud.google.com/blog/products/application-development/gemini-cloud-assist-at-next26) |
| `sdo-20260602-github-review-actions` | 变更接入、代码评审与合并准入 | 已证实事实 | GitHub 发布评审上下文扩展和 Actions 失败修复能力 | [GitHub](https://github.blog/changelog/2026-06-02-shape-copilot-code-review-around-your-team/) |
| `sdo-20260609-datadog-release-loop` | 可观测与上线后校验 | 早期信号 | 生产遥测闭环到代码修复与发布验证 | [Datadog](https://www.datadoghq.com/blog/dash-2026-new-feature-roundup-keynote/) |
| `sdo-20260617-aws-release-management` | 发布与渐进式交付 | 早期信号 | 同一 Agent 连接代码、流水线、拓扑与生产风险 | [AWS](https://aws.amazon.com/blogs/aws/aws-devops-agent-adds-release-management-capabilities-to-assess-code-changes-before-production-preview/) |
| `sdo-20260630-harness-worker-agents` | 流水线编排与调度 | 已证实事实 | Worker Agents 可作为受 RBAC、OPA、审批和审计治理的流水线步骤 | [Harness](https://www.harness.io/blog/introducing-autonomous-worker-agents) |
| `sdo-20260601-pagerduty-parallel-investigation` | 故障诊断、事件响应与自动修复 | 已证实事实 | PagerDuty 公布协调器并行派生假设调查 Agent 的架构 | [PagerDuty](https://www.pagerduty.com/eng/inside-pagerdutys-sre-agent-how-we-built-deep-incident-investigation/) |
| `sdo-20260609-google-secops-agents` | 安全运营 | 已证实事实 | Google SecOps 使用调查 Agent，并由确定性 Playbook 与人工控制高风险处置 | [Google Cloud](https://cloud.google.com/blog/products/identity-security/detecting-and-containing-powered-threats-with-google-security-operations-agents) |
| `sdo-20260615-multicloud-sre-orchestration` | 云、Kubernetes 与平台运维 | 分析判断 | 多云 SRE 转向协调器、专业 Agent 与知识图谱 | [Dynatrace](https://www.dynatrace.com/news/blog/orchestrate-multicloud-ai-agents-for-autonomous-incident-resolution/)、[Komodor](https://komodor.com/blog/multi-agent-ai-sre-has-landed-and-its-built-for-your-most-complex-stacks/) |
| `sdo-20260603-alibaba-agentic-ops` | 安全运营 | 早期信号 | 国内 Agentic Ops 开始公开架构与 RCA 评测 | [Alibaba Cloud](https://www.alibabacloud.com/blog/alibaba-cloud-releases-rca-benchmark-the-industrys-first-open-source-root-cause-analysis-benchmark-system-for-agentic-ops_603252) |

可演进的完整记录见 [基线信号库](./signals/baseline.md)。

## 待审核来源与检索词

- [P0/P1 候选来源](./sources.md)
- [基线检索词](./queries.md)
- [完整研究底稿](../../research/baseline-research.md)

## 覆盖缺口

- X、LinkedIn 登录态尚未完成可靠只读验证，短周期人物信号缺失。
- 视频、播客与会议转录未系统覆盖。
- 证据明显偏厂商官方发布；效果指标和自主执行程度缺少独立复现。
- 构建缓存、制品管理和供应链签名领域发现的 Agentic 信号较少，不能据此推断领域没有进展。
- 国内云厂商和企业内部工程实践仍需定向补充。
