# AI SRE Open Source Watchlist and Scrape Plan

Purpose: track open-source AI, SRE, DevOps, DevSecOps, cloud, platform engineering, and Kubernetes projects that can inform forecasting, planning, and implementation for the AI Incident Investigator for EKS.

Last checked: June 6, 2026.

## How to Use This File

Use this as a practical research and implementation backlog:

1. Review the projects in priority order.
2. Scrape public metadata and documentation, not private data.
3. Extract implementation patterns, architecture ideas, integrations, query examples, and risk controls.
4. Convert useful patterns into labs, architecture decisions, and PRD updates.
5. Re-check fast-moving projects monthly before using them for planning.

## Highest-Priority Projects

These are the strongest projects to study first for an AI-powered SRE platform.

| Project | URL | Why It Matters | What to Scrape or Study |
| --- | --- | --- | --- |
| Aurora | https://github.com/Arvo-AI/aurora | Open-source agentic incident management and RCA for SREs. Integrates with cloud, Kubernetes, Grafana, PagerDuty, Slack, and more. | Agent architecture, LangGraph workflow, integration list, RCA prompts, incident flow, tool schemas, README, issues, releases. |
| K8sGPT | https://github.com/k8sgpt-ai/k8sgpt | Mature Kubernetes AI troubleshooting project. Strong fit for cluster diagnostics and SRE assistant patterns. | Analyzer catalog, CLI flow, Kubernetes issue detection patterns, integrations, remediation hints, operator model. |
| K8sGPT Operator | https://github.com/k8sgpt-ai/k8sgpt-operator | Kubernetes-native way to run AI diagnostics inside clusters. | CRDs, controller pattern, RBAC scope, Helm chart, reconciliation flow, cluster-safe deployment pattern. |
| Robusta | https://github.com/robusta-dev/robusta | Kubernetes alert enrichment, grouping, runbooks, Slack workflows, and AI enrichment. | Alert enrichment patterns, playbooks, Prometheus integration, Slack message design, remediation guardrails. |
| BotKube | https://github.com/kubeshop/botkube | Kubernetes ChatOps and event-driven cluster interaction. Useful for Slack/Teams/PagerDuty UX ideas. | Event routing, Kubernetes recommendations, plugin architecture, chat workflows, command permissions. |
| Langfuse | https://github.com/langfuse/langfuse | Open-source LLM observability, prompt management, evals, and datasets. | Prompt/version management, tracing, eval dataset structure, cost tracking, OpenTelemetry integration. |
| OpenLLMetry | https://github.com/traceloop/openllmetry | OpenTelemetry-based observability for LLM applications. | GenAI tracing instrumentation, span attributes, SDK integrations, OTLP export patterns. |
| OpenLIT | https://github.com/openlit/openlit | OpenTelemetry-native LLM observability with GPU monitoring, guardrails, evals, and prompt management. | LLM telemetry, Grafana integration, guardrails, evaluation patterns, GPU and cost metrics. |
| OpenObserve | https://github.com/openobserve/openobserve | Open-source observability platform for logs, metrics, traces, pipelines, and LLM observability. | Data model, pipeline concepts, log/trace search UX, natural-language query ideas. |
| OpenTelemetry Collector Contrib | https://github.com/open-telemetry/opentelemetry-collector-contrib | Core building block for collecting infrastructure, app, cloud, Kubernetes, and AI telemetry. | Receivers, processors, exporters, Kubernetes metadata enrichment, sampling, pipelines. |

## Kubernetes RCA and AIOps Projects

These are useful for implementation ideas, even when some are smaller or early-stage.

| Project | URL | Use |
| --- | --- | --- |
| Awesome AI SRE | https://github.com/agamm/awesome-ai-sre | Curated list to monitor the AI-SRE market and discover new tools. |
| AIOpsGraph | https://github.com/Aditya01237/AIOpsGraph | Graph-RAG idea for Kubernetes RCA. Study graph schema and RCA flow if maintained. |
| Kubernetes AIOps Evidence Graph | https://github.com/ShreyashDarade/Kubernetes-AIOps-Evidence-Graph | Evidence graph pattern for detection, RCA, and remediation. |
| k8s-aiops-investigator | https://github.com/mfzs/k8s-aiops-investigator | Kubernetes incident investigation and remediation patterns. |
| AI-Powered Kubernetes Troubleshooting Assistant | https://github.com/sd031/AI-Powered-Kubernetes-Troubleshooting-Assistant | CLI and web troubleshooting flow, local model support, runbook generation. |
| Kubemedic | https://github.com/robert-cronin/kubemedic | Kubernetes diagnostics assistant pattern. |
| Scorching AIOps | https://github.com/necrustulum/scorching-aiops | Advanced ideas: eBPF, causal graphs, Neo4j, LangGraph, GitOps, Ollama, remediation. |

## DevSecOps and Cloud Security Projects

These are important because the SRE agent should eventually explain security and compliance signals, not only availability incidents.

| Project | URL | Why It Matters | What to Scrape or Study |
| --- | --- | --- | --- |
| Trivy | https://github.com/aquasecurity/trivy | Standard open-source scanner for vulnerabilities, misconfigurations, secrets, SBOM, Kubernetes, IaC, and cloud. | Finding schemas, severity model, Kubernetes scanning output, SARIF/SBOM output, remediation text. |
| Kubescape | https://github.com/kubescape/kubescape | Kubernetes security posture, risk analysis, compliance, and misconfiguration scanning. | Frameworks, controls, risk scoring, cluster posture reports, compliance mappings. |
| Falco | https://github.com/falcosecurity/falco | Runtime security detection for cloud-native workloads using rules and eBPF/syscall signals. | Rule format, event fields, Kubernetes metadata, runtime threat examples. |
| Agent BOM | https://github.com/msaad00/agent-bom | AI supply-chain and agent security concepts: MCP, SBOM/SARIF, runtime enforcement, compliance evidence. | AI-agent security model, SBOM/SARIF handling, compliance output, MCP risks. |
| Aegis MCP | https://github.com/raghulvj01/aegis-mcp | MCP server for DevSecOps tasks: cloud audits, CVE scanning, secrets detection, Kubernetes security. | MCP tool schemas, security automation scope, least-privilege patterns. |
| AuditVision | https://github.com/vsenatorov/auditvision | Kubernetes/OpenShift audit log explorer with AI risk scoring. | Audit log fields, risk scoring patterns, compliance workflows. |

## Reliability, Events, and Chaos Data Sources

These projects can help generate or collect realistic failure data for model evaluation and forecasting.

| Project | URL | Use |
| --- | --- | --- |
| Kubernetes event exporter | https://github.com/caicloud/event_exporter | Export Kubernetes events to Prometheus-style metrics. Useful for RCA timelines. |
| Kubernetes events exporter | https://github.com/ownkube/kubernetes-events-exporter | Event export to many sinks such as Kafka, Elasticsearch, Slack, webhooks, AWS/GCP services, and Loki. |
| LitmusChaos | https://github.com/litmuschaos/litmus | Chaos experiments for reliability validation and incident eval datasets. |
| Chaos Mesh | https://github.com/chaos-mesh/chaos-mesh | Kubernetes-native chaos engineering platform for fault injection and RCA testing. |
| APO | https://github.com/CloudDetail/apo | Observability platform combining OpenTelemetry, eBPF, and LLM-assisted troubleshooting. |
| DeepFlow | https://github.com/deepflowio/deepflow | eBPF observability, distributed tracing, and profiling. Useful for zero-code telemetry patterns. |

## What Data to Scrape

Scrape public project data that helps with architecture, forecasting, planning, and implementation. Avoid scraping private organizational data, credentials, personal data, or anything prohibited by a project's terms.

Recommended data:

- Repository metadata:
  - Name.
  - Owner.
  - URL.
  - Description.
  - Topics.
  - Language.
  - Stars.
  - Forks.
  - Open issue count.
  - Created date.
  - Updated date.
  - Default branch.
  - License.
- README and docs:
  - Architecture diagrams.
  - Feature lists.
  - Installation steps.
  - Integration lists.
  - Security model.
  - Configuration examples.
  - Query examples.
- Releases:
  - Release date.
  - Major feature changes.
  - Breaking changes.
  - Security fixes.
  - Integration additions.
- Issues and discussions:
  - Common failure modes.
  - Feature requests.
  - Integration pain points.
  - Security concerns.
  - Production deployment issues.
- Code and config examples:
  - Tool schemas.
  - Agent workflows.
  - Helm charts.
  - CRDs.
  - RBAC manifests.
  - PromQL, LogQL, TraceQL, CloudWatch, and Kubernetes query examples.
  - Slack, Teams, PagerDuty, or webhook payload examples.

## Dataset Schema for Local Tracking

Use this schema if you create a local repo tracker later:

```yaml
project:
  name:
  owner:
  url:
  category:
  primary_use_case:
  relevance_to_ai_incident_investigator:
  maturity:
  stars:
  forks:
  open_issues:
  last_updated:
  license:
  languages:
  integrations:
  scrape_targets:
    - readme
    - docs
    - releases
    - issues
    - helm_charts
    - crds
    - rbac
    - query_examples
  useful_patterns:
  risks:
  next_action:
```

## Forecasting Signals to Track

Track these monthly to understand where the AI-SRE market is moving:

- Growth in AI-SRE repositories and stars.
- New integrations with Grafana, Prometheus, Loki, Tempo, PagerDuty, Slack, AWS, Azure, and GCP.
- Movement from chatbots to agentic investigation workflows.
- Use of knowledge graphs, evidence graphs, and dependency graphs for RCA.
- Use of OpenTelemetry semantic conventions for LLM and agent observability.
- Increased focus on human approval, audit logs, and least-privilege tools.
- Shift from generic runbook bots to telemetry-grounded incident investigators.
- More open-source support for local models through Ollama or similar tools.
- Security focus around MCP, tool permissions, prompt injection, SBOM, SARIF, and AI supply chain.

## Implementation Plan for This Workspace

### Phase 1: Research and Scrape

- Create a local repo tracker file or script.
- Pull public metadata for the priority projects.
- Summarize each project into one page:
  - What it does.
  - How it is architected.
  - What it integrates with.
  - What can be reused for EKS incident investigation.
  - What risks or gaps exist.

### Phase 2: Architecture Extraction

Extract patterns from:

- Aurora for incident agent workflow.
- K8sGPT for Kubernetes analyzers.
- Robusta for alert enrichment and Slack flow.
- BotKube for ChatOps.
- Langfuse/OpenLLMetry/OpenLIT for LLM observability.
- Trivy/Kubescape/Falco for DevSecOps signals.
- LitmusChaos/Chaos Mesh for synthetic incident generation.

### Phase 3: Build MVP

Implement a read-only AI Incident Investigator:

- Alert webhook receiver.
- Mimir query tool.
- Loki query tool.
- Tempo query tool.
- Kubernetes events query tool.
- CloudWatch alarm and metric query tool.
- Deployment history query tool.
- RCA timeline generator.
- Slack, Teams, or PagerDuty summary output.

### Phase 4: Evaluation Dataset

Use chaos experiments and known scenarios to create test cases:

- OOMKilled.
- CrashLoopBackOff.
- Node pressure.
- CPU throttling.
- Failed rollout.
- Dependency latency.
- TLS/certificate error.
- DNS failure.
- CloudWatch alarm correlation.
- Vulnerability or runtime security signal during incident.

### Phase 5: Planning and ROI

Create monthly planning metrics:

- MTTR reduction estimate.
- Alert compression ratio.
- Time to first RCA hypothesis.
- Engineer hours saved.
- Most common incident patterns.
- High-value integrations not yet implemented.
- Security and compliance risks to address before automation.

## Recommended First Five Deep Dives

1. Aurora: agentic incident management and RCA architecture.
2. K8sGPT plus K8sGPT Operator: Kubernetes analyzer and in-cluster AI diagnostic model.
3. Robusta: alert enrichment, grouping, runbooks, Slack, and remediation patterns.
4. Langfuse or OpenLLMetry: tracing and evaluating your own AI agent.
5. Trivy plus Kubescape plus Falco: DevSecOps and runtime security signals for the future incident investigator.

## Related Workspace Files

- [../AI-Powered SRE Copilot Project Plan.md](../AI-Powered%20SRE%20Copilot%20Project%20Plan.md)
- [../00-start-here/2026-ai-roadmap.md](../00-start-here/2026-ai-roadmap.md)
- [../10-hands-on-labs/lab-backlog.md](../10-hands-on-labs/lab-backlog.md)
- [../11-reference-architecture/production-ai-app-checklist.md](../11-reference-architecture/production-ai-app-checklist.md)

