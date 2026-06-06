# AI-Powered SRE Copilot PRD

## Product Name

AI Incident Investigator for EKS

## Document Purpose

This PRD captures a production-focused AI/SRE project idea for an organization running EKS with Grafana Loki, Mimir, Tempo, alerting, and AWS CloudWatch. The goal is to build an AI-assisted incident investigation system that reduces MTTR, reduces alert fatigue, improves RCA quality, and creates measurable business ROI.

This should be treated as a flagship end-to-end project for this workspace.

## Background

The current production support/SRE stack is already aligned with where AI-driven SRE platforms are going:

- EKS for Kubernetes workloads.
- Grafana Mimir for metrics.
- Grafana Loki for logs.
- Grafana Tempo for traces.
- Grafana Alerting or alertmanager-style alerting.
- AWS CloudWatch alarms, metrics, and logs.
- Deployment history from ArgoCD, GitHub Actions, Helm, or Kubernetes rollout events.

The common mistake is to start with a generic chatbot. The higher-ROI path is to build an investigation system that correlates telemetry and produces actionable incident context for engineers.

## Problem Statement

Production incidents require engineers to manually inspect metrics, logs, traces, alerts, Kubernetes events, deployment history, and cloud signals under time pressure. This creates slow triage, repeated manual investigation, alert fatigue, inconsistent RCA quality, and missed opportunities to detect risk earlier.

The system should reduce the manual work required to answer:

- What changed?
- What service is affected?
- What evidence supports the likely root cause?
- What is the blast radius?
- What should the SRE team check next?
- Which runbook or past incident is most relevant?

## Target Users

- Production support engineers.
- SREs.
- DevOps engineers.
- Platform engineers.
- Incident commanders.
- Engineering managers reviewing incident trends and ROI.

## Business Goals

- Reduce P1/P2 investigation time from 30-60 minutes to 2-5 minutes for the first RCA hypothesis.
- Reduce alert fatigue by grouping related alerts into one incident narrative.
- Improve postmortem quality with evidence-backed timelines.
- Increase reliability by detecting Kubernetes degradation patterns earlier.
- Reduce toil by automating telemetry collection, not production remediation.
- Provide measurable ROI through MTTR reduction, reduced engineering time, and lower incident impact.

## Highest-ROI SRE AI Use Cases

1. Incident investigation.
2. Root cause analysis.
3. Alert noise reduction.
4. Capacity forecasting.
5. Auto-generated postmortems.
6. Runbook automation.
7. Kubernetes health intelligence.

## Product Vision

When a P1 or P2 alert fires, the AI Incident Investigator automatically gathers telemetry from Grafana and AWS sources, correlates the signals, identifies likely root-cause hypotheses, and sends an evidence-backed RCA summary to Slack, Teams, or PagerDuty within 2-5 minutes.

Example output:

```text
Incident: checkout-service degradation

Likely Root Cause:
checkout-service v2.4.1 deployment caused pod restart storms due to memory pressure.

Confidence:
82%

Evidence:
- Error rate increased 5 minutes after deployment.
- OOMKilled events detected in checkout pods.
- Memory usage increased 43%.
- Trace latency increased from 120ms to 1.8s.
- CloudWatch alarm entered ALARM state after rollout.

Suggested Next Actions:
1. Inspect checkout-service memory request and limit.
2. Compare v2.4.1 resource usage with previous deployment.
3. Review HPA behavior and node pressure.
4. Consider rollback if error budget burn remains high.

Human approval required before any remediation.
```

## Current Manual Workflow

```text
Alert fires
  |
Engineer opens Grafana
  |
Checks Mimir metrics
  |
Checks Loki logs
  |
Checks Tempo traces
  |
Checks Kubernetes events
  |
Checks deployment history
  |
Finds likely root cause
```

Typical duration: 30-60 minutes.

## Proposed AI Workflow

```text
P1/P2 alert fires
  |
Incident investigator starts
  |
Pulls metrics, logs, traces, events, alarms, and deployments
  |
Builds timeline and dependency context
  |
Scores root-cause hypotheses
  |
Posts RCA summary to Slack, Teams, or PagerDuty
  |
SRE reviews evidence and approves any next action
```

Target duration: 2-5 minutes for the first useful investigation report.

## Reference Architecture

```text
EKS
 |
 |-- Mimir metrics
 |-- Loki logs
 |-- Tempo traces
 |-- Kubernetes Events API
 |-- Deployment events
 |-- CloudWatch alarms and metrics
 |
 v
Observability Data Lake / Query Layer
 |
 v
AI Correlation Layer
 |
 v
SRE Agent
 |
 v
Slack / Teams / PagerDuty / Incident Tool
```

## Core Data Sources

- Grafana Mimir metrics.
- Grafana Loki logs.
- Grafana Tempo traces.
- Kubernetes Events API.
- AWS CloudWatch alarms and metrics.
- Deployment events from ArgoCD, GitHub Actions, Helm, or Kubernetes rollout history.
- Runbooks, SOPs, architecture docs, and previous postmortems.
- Optional: AWS Cost and Usage Reports, Karpenter metrics, and cluster autoscaler signals.

## Primary MVP: AI Root Cause Analysis

### User Story

As a production support engineer or SRE, I want an AI investigator to automatically gather and correlate telemetry after a P1/P2 alert so that I can understand the likely root cause, evidence, blast radius, and next steps within minutes.

### MVP Capabilities

- Accept an incident trigger from an alert webhook.
- Identify the affected service, namespace, cluster, and time window.
- Query Mimir for service, pod, node, and cluster metrics.
- Query Loki for relevant logs and error clusters.
- Query Tempo for slow or failing traces.
- Query Kubernetes events for pod restarts, OOMKilled events, evictions, scheduling failures, and node pressure.
- Query deployment history for recent rollouts.
- Query CloudWatch for related alarms or AWS-side anomalies.
- Produce a timeline of what changed before, during, and after the alert.
- Generate likely root-cause hypotheses with confidence scores.
- Post the incident summary to Slack, Teams, or PagerDuty.
- Require human approval before any remediation action.

### MVP Non-Goals

- No autonomous production changes.
- No direct rollback execution in the first release.
- No unrestricted cluster-admin access.
- No training on private data without governance approval.
- No replacement for SRE judgment or incident command.

## Use Case 1: AI Root Cause Analysis

Input:

```text
High error rate alert for checkout-service
```

Agent actions:

1. Pulls Mimir metrics.
2. Finds affected service and namespace.
3. Queries Loki logs.
4. Queries Tempo traces.
5. Queries Kubernetes events.
6. Queries deployment history.
7. Queries CloudWatch alarms.

Output:

```text
Root Cause Probability: 82%

Likely Cause:
checkout-service deployment

Evidence:
- Error rate increased 5 minutes after deployment.
- OOMKilled events detected.
- Memory usage increased 43%.
- Trace latency increased from 120ms to 1.8s.
```

## Use Case 2: Alert Deduplication

Problem:

```text
1000 alerts may represent 1 outage.
```

The agent should group related alert signals:

- Pod restart.
- CPU spike.
- Latency increase.
- Error rate increase.
- CloudWatch alarm.

into one incident:

```text
Single Incident:
checkout-service degradation
```

Expected result: lower alert fatigue and faster incident commander understanding.

## Use Case 3: Kubernetes Failure Prediction

Goal: detect likely outage patterns 15-30 minutes before user impact or before severity escalates.

Signal examples:

```text
container_cpu_usage_seconds_total
container_memory_working_set_bytes
node_memory_available_bytes
kube_pod_container_status_restarts_total
```

Additional signals:

- Node pressure.
- OOM events.
- CPU throttling.
- HPA behavior.
- Pod evictions.
- Network errors.
- Karpenter or autoscaler behavior.

The first version should use anomaly detection and heuristic scoring before attempting custom model training.

## Use Case 4: AI-Powered Runbooks

Build a RAG system over:

- Runbooks.
- Postmortems.
- Architecture docs.
- Grafana dashboard notes.
- Kubernetes docs.
- Internal SOPs.

Example question:

```text
Why are checkout pods restarting?
```

Example answer:

```text
This matches Incident #1247.

Suggested Actions:
1. Check memory limits.
2. Verify HPA.
3. Inspect deployment rollout.

Runbook:
RB-104
```

## Use Case 5: Loki Log Intelligence

The agent should cluster high-volume logs into meaningful categories:

- Database connection error.
- TLS error.
- Timeout error.
- Authentication error.
- Dependency unavailable.

It should also explain common operational errors.

Example input:

```text
x509 certificate signed by unknown authority
```

Example output:

```text
Probable Causes:
- Expired certificate.
- Missing CA bundle.
- Trust store mismatch.
- Incorrect service mesh or ingress certificate chain.
```

## Use Case 6: Tempo Trace Intelligence

Tempo traces should be treated as a high-value signal for service dependency and blast-radius analysis.

The agent should analyze:

- Trace span duration.
- Dependency graph.
- Service calls.
- Retries.
- Failures.
- Downstream impact.

Example:

```text
Checkout latency spike
```

Output:

```text
Root Service:
payment-api

Downstream Impact:
checkout
orders
inventory

Blast Radius:
27 services
```

## Use Case 7: Cloud Cost and Reliability AI

Data sources:

- CloudWatch.
- AWS Cost and Usage Reports.
- Mimir metrics.
- Karpenter metrics.

Example question:

```text
Why did EKS cost increase 20% yesterday?
```

Example answer:

```text
Node group autoscaled.

Cause:
checkout deployment

Pods increased:
250 -> 500

Cost increase:
$812
```

## 90-Day Build Plan

### Month 1: SRE Copilot

Data sources:

- Loki.
- Mimir.
- Tempo.
- CloudWatch.

Capabilities:

- Search telemetry.
- Explain incidents.
- Query dashboards or saved panels.
- Generate an initial incident summary.
- Avoid production automation.

Deliverables:

- Alert webhook receiver.
- Read-only telemetry query tools.
- First Slack or Teams summary.
- Basic prompt and tool-call logging.

### Month 2: AI Incident Investigator

Triggered by:

```text
P1
P2
```

Automatically gathers:

- Metrics.
- Logs.
- Traces.
- Kubernetes events.
- Deployment history.
- CloudWatch alarms.

Deliverables:

- RCA hypothesis report.
- Evidence timeline.
- Blast-radius summary.
- Alert grouping logic.
- Evaluation dataset from past incidents or synthetic incidents.

### Month 3: Remediation Suggestions

Example:

```text
OOMKilled
```

AI suggestion:

```text
Increase memory request from 256Mi to 512Mi.
```

Controls:

- Human approval required.
- Suggested actions only.
- No autonomous production changes.
- Audit log for every recommendation and approval.

Deliverables:

- Remediation recommendation engine.
- Runbook RAG integration.
- Approval workflow.
- Postmortem draft generator.

## Emerging Advanced Architecture Pattern

```text
Telemetry
  |
Knowledge Graph
  |
LLM
  |
RCA Agent
  |
Human Approval
  |
Automation
```

For this project, start with read-only investigation. Add human-approved remediation only after the system has proven accuracy, reliability, and auditability.

## Success Metrics

- Time to first RCA hypothesis.
- Mean time to acknowledge.
- Mean time to resolution.
- Number of alerts grouped into incidents.
- Percentage of incidents with useful AI-generated timeline.
- RCA suggestion acceptance rate.
- False positive and false confidence rate.
- Engineer time saved per P1/P2.
- Reduction in repeated incident classes.
- Postmortem draft completion time.

## Security and Governance Requirements

- Use read-only credentials for MVP telemetry tools.
- Scope Kubernetes permissions by namespace where possible.
- Store secrets in AWS Secrets Manager, Parameter Store, or approved secret management.
- Never expose secrets in prompts, logs, traces, or incident summaries.
- Redact sensitive data from logs before sending to an LLM.
- Log every model call and tool call.
- Require human approval for remediation.
- Keep an allowlist of supported queries and tools.
- Add prompt-injection defenses for retrieved runbooks, logs, and docs.
- Preserve incident evidence for audit and postmortem review.

## Evaluation Strategy

Create an incident evaluation dataset with:

- Past incidents.
- Synthetic Kubernetes failures.
- Known root causes.
- Expected evidence.
- Expected timeline.
- Expected next actions.

Evaluate:

- Root-cause accuracy.
- Evidence quality.
- Timeline correctness.
- Hallucination rate.
- Latency.
- Cost per investigation.
- Safety behavior when data is missing or contradictory.

## Production Readiness Checklist

- [ ] Read-only access model documented.
- [ ] Tool schemas versioned.
- [ ] Query timeouts and rate limits implemented.
- [ ] Slack, Teams, or PagerDuty integration tested.
- [ ] Prompt and response logs captured safely.
- [ ] Secrets redaction tested.
- [ ] Incident eval dataset created.
- [ ] Human approval workflow implemented before remediation.
- [ ] Rollback and disable switch documented.
- [ ] Cost budget and model usage alerts configured.

## Workspace Alignment

- Learning roadmap: [00-start-here/2026-ai-roadmap.md](00-start-here/2026-ai-roadmap.md)
- AI agents: [03-ai-agents](03-ai-agents)
- MCP and context: [04-mcp-model-context-protocol](04-mcp-model-context-protocol)
- RAG and knowledge systems: [05-rag-and-knowledge-systems](05-rag-and-knowledge-systems)
- LLMOps, MLOps, AIOps: [06-mlops-llmops-aiops](06-mlops-llmops-aiops)
- Observability, evals, and security: [07-ai-observability-evals-security](07-ai-observability-evals-security)
- Cloud AI platforms: [08-cloud-ai-platforms](08-cloud-ai-platforms)
- Hands-on labs: [10-hands-on-labs](10-hands-on-labs)
- Reference architecture: [11-reference-architecture](11-reference-architecture)
- Resume and ATS conversion: [14-resume-and-ats](14-resume-and-ats)

## External References

Verified on June 6, 2026:

- [Grafana AI Observability and Assistant](https://grafana.com/products/cloud/ai-observability/)
- [AWS CloudWatch investigations](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Investigations.html)
- [Grafana AI documentation](https://grafana.com/docs/grafana-cloud/machine-learning/intro/)
- [Grafana Mimir 3.0 announcement](https://grafana.com/press/2025/11/05/grafana-labs-launches-mimir-3.0-expanding-open-observability-at-scale-at-kubecon--cloudnativecon-north-america-2025/)
- [Simplifying Root Cause Analysis in Kubernetes with StateGraph and LLM](https://arxiv.org/abs/2506.02490)

