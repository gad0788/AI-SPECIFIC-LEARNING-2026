# Production AI App Checklist

## Architecture

- [ ] Clear user workflow.
- [ ] Model provider selected with fallback plan.
- [ ] Prompt and tool contracts versioned.
- [ ] Data sources identified and access-controlled.
- [ ] RAG pipeline has ingestion, re-indexing, and deletion flow.
- [ ] Agent tools are least-privilege and idempotent where possible.

## Security

- [ ] Secrets in Key Vault/Secrets Manager/parameter store.
- [ ] No secrets in prompts, traces, or logs.
- [ ] Prompt injection mitigations.
- [ ] MCP servers reviewed and approved.
- [ ] Human approval for write/destructive actions.
- [ ] Audit logs for model calls and tool calls.

## Reliability

- [ ] Timeouts and retries.
- [ ] Rate-limit handling.
- [ ] Provider fallback.
- [ ] Circuit breaker for failing tools.
- [ ] Queue or async processing for long tasks.
- [ ] Incident runbook.

## Observability

- [ ] Model call traces.
- [ ] Tool call traces.
- [ ] Retrieval traces.
- [ ] Token and cost metrics.
- [ ] Latency percentiles.
- [ ] Error and refusal rates.
- [ ] Eval results tracked over time.

## Delivery

- [ ] CI tests.
- [ ] Prompt/eval regression tests.
- [ ] IaC for infrastructure.
- [ ] Staging environment.
- [ ] Rollback plan.
- [ ] Cost budget and alerts.

