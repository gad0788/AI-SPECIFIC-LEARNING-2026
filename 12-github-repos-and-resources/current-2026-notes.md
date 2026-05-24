# Current 2026 Notes

This file captures research findings that are time-sensitive. Re-check official docs before using these in production.

## MCP and Agent Tooling

- Codex supports MCP server configuration through `codex mcp` and `~/.codex/config.toml`.
- GitHub has an official MCP server at `https://api.githubcopilot.com/mcp/`.
- GitLab documents HTTP MCP at `https://gitlab.com/api/v4/mcp` for GitLab.com and `https://<gitlab.example.com>/api/v4/mcp` for self-managed.
- Atlassian recommends the newer endpoint `https://mcp.atlassian.com/v1/mcp/authv2`; older SSE endpoint support is scheduled to end after June 30, 2026.
- Linear documents Codex setup with `codex mcp add linear --url https://mcp.linear.app/mcp`.
- Cloudflare documents `https://mcp.cloudflare.com/mcp`.
- Vercel documents `https://mcp.vercel.com`.
- Sentry documents `https://mcp.sentry.dev/mcp`.

## Production AI Trends to Watch

- GenAI observability is standardizing around OpenTelemetry semantic conventions for model calls, tool calls, token usage, and agent spans.
- AI agents are increasingly treated as production workloads with identity, permissions, audit logs, registries, memory, and deployment runtimes.
- MCP improves tool interoperability, but increases security risk if servers are over-privileged or untrusted.
- For DevOps/SRE roles, the most valuable AI skill is not just prompting. It is building reliable, observable, secure, cost-aware AI systems.

