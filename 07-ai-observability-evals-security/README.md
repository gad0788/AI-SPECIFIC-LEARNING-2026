# AI Observability, Evals, and Security

## Observability

Track:

- Model provider and model name.
- Prompt version.
- Input/output token counts.
- Latency by step.
- Retrieval latency and retrieved document IDs.
- Tool call names, arguments, status, and duration.
- Errors, retries, timeouts, rate limits.
- Cost by user, feature, environment, and tenant.

OpenTelemetry GenAI semantic conventions are becoming an important standard:

- https://opentelemetry.io/docs/specs/semconv/gen-ai/
- https://opentelemetry.io/blog/2026/genai-observability/

## Evals

Test:

- Prompt regression.
- Structured output validity.
- RAG retrieval quality.
- Faithfulness to source context.
- Tool-call correctness.
- Safety and refusal behavior.
- Latency and cost budgets.

Tools to explore:

- Ragas
- DeepEval
- LangSmith
- Langfuse
- Arize Phoenix
- MLflow GenAI

## Security

Threats:

- Prompt injection.
- Data exfiltration.
- Tool misuse.
- Over-scoped MCP tokens.
- Secrets in prompts/logs.
- Untrusted retrieved content.
- Supply-chain risk from MCP servers and agent tools.

Controls:

- Least privilege.
- Secret redaction.
- Human approval.
- Output validation.
- Tool allowlists.
- Network egress control.
- Audit logs.
- Eval tests for unsafe behavior.

