# LLMs and Prompt Engineering

## Core Topics

- Messages: system/developer/user style instructions depending on provider.
- Context window: how much text the model can consider.
- Temperature/top-p: controls randomness, not correctness.
- Structured output: JSON schemas or strict output contracts.
- Tool calling: model selects a function/tool and provides arguments.
- Streaming: return partial output for latency-sensitive UX.
- Reasoning models: trade latency/cost for harder tasks.

## Prompt Patterns

- Role and goal: define what the model is doing.
- Context: provide only relevant facts.
- Constraints: define boundaries, style, security, and output format.
- Examples: show desired behavior.
- Verification: ask the model to cite evidence, check assumptions, or return confidence.
- Refusal/safety: define what the model must not do.

## Practice Tasks

- Convert unstructured incident notes into JSON.
- Summarize a Kubernetes outage timeline.
- Generate Terraform review comments.
- Extract action items from a postmortem.
- Compare two architecture options with tradeoffs.

