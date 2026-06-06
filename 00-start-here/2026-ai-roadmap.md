# 2026 AI Upskilling Roadmap

Purpose: provide an end-to-end AI learning path that AI agents and humans can reference when planning study, labs, projects, and portfolio evidence in this workspace.

Use this roadmap alongside:

- [START-HERE.md](START-HERE.md)
- [ROADMAP.md](ROADMAP.md)
- [../13-weekly-progress-log/progress-log.md](../13-weekly-progress-log/progress-log.md)
- [../14-resume-and-ats/resume-skill-bank.md](../14-resume-and-ats/resume-skill-bank.md)

## Agent Reference Rule

When an AI agent works in this project, use this file to understand the full learning sequence before suggesting notes, labs, project plans, resume bullets, or architecture work. Keep recommendations aligned with the phase order unless the user explicitly asks to jump ahead.

## Phase 1: Fundamentals

Goal: build a strong foundation in how modern language models work and how to communicate with them effectively.

Focus areas:

- LLMs and how they process language.
- Tokens and tokenization.
- Context windows and context limits.
- Inference and model behavior at runtime.
- Prompt engineering patterns:
  - Role-based prompting.
  - Few-shot prompting.
  - Chain-of-thought style reasoning prompts.
- Model landscape:
  - Frontier models.
  - Open-source models.
  - Coding models.
  - Local models.

Workspace alignment:

- Use [../01-ai-fundamentals](../01-ai-fundamentals) for foundational notes.
- Use [../02-llms-and-prompt-engineering](../02-llms-and-prompt-engineering) for LLM and prompting practice.

## Phase 2: AI-Powered Engineering

Goal: move beyond chat-based AI into AI-assisted engineering workflows.

Focus areas:

- AI coding agents.
- GitHub Copilot and coding assistant workflows.
- Agent-assisted development patterns.
- Workflow automation tools such as n8n.
- Turning repeatable engineering tasks into AI-assisted workflows.

Workspace alignment:

- Use [../09-coding-assistants](../09-coding-assistants) for coding assistant workflows.
- Use [../03-ai-agents](../03-ai-agents) for agent behavior, tool use, and orchestration.
- Use [../10-hands-on-labs](../10-hands-on-labs) for workflow automation labs.

## Phase 3: AI APIs

Goal: learn how to integrate AI models into real applications through APIs.

Focus areas:

- Calling AI model APIs from applications.
- API authentication and secret handling.
- Security controls for AI applications.
- Rate limiting and request management.
- Cost management and usage monitoring.
- Model routing and fallback strategies.
- OpenRouter-style routing concepts.

Workspace alignment:

- Use [../10-hands-on-labs](../10-hands-on-labs) for API integration labs.
- Use [../07-ai-observability-evals-security](../07-ai-observability-evals-security) for security, evaluation, cost, and reliability notes.
- Use [../06-mlops-llmops-aiops](../06-mlops-llmops-aiops) for production operations concepts.

## Phase 4: Local Models

Goal: understand how to run and experiment with open-source models locally.

Focus areas:

- Ollama.
- Hugging Face.
- Docker Model Runner.
- Model weights.
- Quantization.
- Fine-tuning concepts.
- Tradeoffs between hosted APIs and local inference.

Workspace alignment:

- Use [../01-ai-fundamentals](../01-ai-fundamentals) for model basics.
- Use [../10-hands-on-labs](../10-hands-on-labs) for local model experiments.
- Use [../08-cloud-ai-platforms](../08-cloud-ai-platforms) when comparing local models with managed cloud AI services.

## Phase 5: Context Engineering

Goal: learn how to give AI systems the right context for large codebases, long-running tasks, and agentic workflows.

Focus areas:

- Context retrieval.
- Managing large codebases with selective context.
- Agent memory:
  - Short-term memory.
  - Long-term memory.
  - Semantic memory.
- Model Context Protocol (MCP).
- Tool-access boundaries and context hygiene.

Workspace alignment:

- Use [../04-mcp-model-context-protocol](../04-mcp-model-context-protocol) for MCP notes and labs.
- Use [../03-ai-agents](../03-ai-agents) for agent memory and tool-use patterns.
- Use [../09-coding-assistants](../09-coding-assistants) for coding-agent context workflows.

## Phase 6: RAG and Knowledge Systems

Goal: implement retrieval-augmented generation systems that let AI use private or proprietary knowledge.

Focus areas:

- Retrieval-Augmented Generation.
- Vector databases.
- Embeddings.
- Chunking and metadata.
- Grounded answers over organizational data.
- Knowledge systems for documents, notes, runbooks, tickets, and repositories.

Workspace alignment:

- Use [../05-rag-and-knowledge-systems](../05-rag-and-knowledge-systems) for RAG, embeddings, vector database notes, and labs.
- Use [../07-ai-observability-evals-security](../07-ai-observability-evals-security) for RAG evaluation, grounding, and security.

## Phase 7: Agentic AI

Goal: learn how to orchestrate multiple AI agents that can plan, coordinate, use tools, and complete tasks.

Focus areas:

- Multi-agent orchestration.
- CrewAI.
- LangChain.
- LangGraph.
- AutoGen.
- Planner, executor, reviewer, and researcher roles.
- Guardrails, permissions, and human approval points.

Workspace alignment:

- Use [../03-ai-agents](../03-ai-agents) for agent design and orchestration.
- Use [../04-mcp-model-context-protocol](../04-mcp-model-context-protocol) for tool and context integration.
- Use [../07-ai-observability-evals-security](../07-ai-observability-evals-security) for agent evaluation, observability, and safety.

## Phase 8: End-to-End Projects

Goal: prove mastery by building complete AI systems that connect concepts from every phase.

Build at least five full-stack AI projects. Candidate projects:

- AI Kubernetes agent.
- AI DevOps team.
- AI-powered SRE copilot.
- RAG assistant over DevOps or SRE runbooks.
- Multi-agent incident-response assistant.

Each project should include:

- A clear problem statement.
- Architecture notes.
- Implementation code.
- Security and cost considerations.
- Evaluation or test strategy.
- Deployment or demo path.
- Resume-ready outcome statements.

Workspace alignment:

- Use [../10-hands-on-labs](../10-hands-on-labs) for lab work.
- Use [../11-reference-architecture](../11-reference-architecture) for diagrams and design notes.
- Use [../12-github-repos-and-resources](../12-github-repos-and-resources) for repo tracking.
- Use [../14-resume-and-ats](../14-resume-and-ats) for converting completed projects into resume bullets.

## End-to-End Study Flow

1. Learn the concept.
2. Write the concept in your own words.
3. Build a small lab.
4. Connect the lab to DevOps, SRE, or cloud engineering.
5. Add evaluation, security, reliability, and cost notes.
6. Convert the work into portfolio evidence.
7. Convert completed evidence into resume bullets.
