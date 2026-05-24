# AI Agents

An AI agent is a system where a model can use tools, observe results, maintain state, and continue working toward a goal.

## Agent Building Blocks

- Model: decides what to do next.
- Tools: APIs/functions/files/search/actions the agent can invoke.
- Instructions: rules, role, boundaries, and success criteria.
- State: task history, memory, intermediate results.
- Planner: decomposes work.
- Executor: performs steps.
- Evaluator/reviewer: checks output and risk.
- Human approval: required for sensitive actions.

## Patterns

- ReAct: reason and act in alternating steps.
- Router: choose the right tool or specialist.
- Planner-executor: plan first, then execute.
- Reflection: critique and improve output.
- Multi-agent: split roles like researcher, builder, reviewer.
- Human-in-the-loop: pause before changes, deletes, spending, deployment, or external messages.

## Production Risks

- Tool over-permission.
- Prompt injection through retrieved content.
- Infinite loops or retry storms.
- Hidden cost growth from long context and repeated calls.
- State corruption and non-idempotent actions.
- Weak auditability.

## DevOps/SRE Agent Ideas

- Incident triage assistant.
- Terraform/Kubernetes reviewer.
- CI failure investigator.
- Runbook retrieval and execution planner.
- Cost anomaly explainer.
- Security finding summarizer.

