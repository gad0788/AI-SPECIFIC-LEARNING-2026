# Hands-on Lab Backlog

Build in increasing difficulty. Each lab should have a README, architecture diagram, setup steps, tests, observability notes, and resume bullet.

## Beginner

- `hello-llm-cli`: CLI that sends prompts to an LLM and returns structured JSON.
- `prompt-patterns`: before/after examples for summarization, extraction, classification, and command generation.
- `embeddings-search`: embed local markdown notes and run similarity search.
- `codex-workflow-lab`: use Codex to inspect a repo, make a change, run tests, and produce a review summary.

## Intermediate

- `devops-rag-assistant`: RAG over your DevOps notes, Terraform modules, Kubernetes runbooks, and interview notes.
- `incident-runbook-agent`: agent that classifies an incident, retrieves a runbook, proposes next steps, and asks for approval before actions.
- `mcp-devops-lab`: connect GitHub/GitLab/Jira/Linear MCP servers and document safe use cases.
- `llm-observability-lab`: instrument LLM calls, retrieval, tool calls, latency, tokens, and errors.
- `rag-eval-pipeline`: CI job that runs retrieval and answer-quality evals on a test dataset.

## Advanced

- `aws-bedrock-agentcore-platform`: deploy an AWS-native agent with IAM-scoped tools, CloudWatch, and CI/CD.
- `multi-agent-sre-assistant`: planner, investigator, remediation proposer, and reviewer agents with human approval.
- `ai-platform-reference-architecture`: production design for multi-tenant AI apps with auth, logging, evals, cost controls, and rollback.
- `prompt-injection-defense-lab`: demonstrate untrusted retrieval content attacks and mitigations.
- `model-routing-gateway`: route requests across providers based on cost, latency, quality, and fallback policy.

