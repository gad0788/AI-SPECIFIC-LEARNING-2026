# MCP - Model Context Protocol

MCP is a standard way for AI clients to connect to tools, APIs, data sources, and context servers.

## What to Learn

- Host/client/server terminology.
- Stdio vs streamable HTTP transport.
- Tools, resources, prompts, and elicitation.
- OAuth and bearer-token auth.
- MCP server permissions and approval modes.
- Local vs remote MCP security boundaries.
- How Codex, Claude Code, Cursor, VS Code, and other clients configure MCP.

## Your Current Codex MCP Status

Known enabled servers from earlier setup:

- `openaiDeveloperDocs`
- `github`
- `gitlab`
- `atlassian`
- `linear`

Some may require login or environment variables before use.

## DevOps MCP Targets

- GitHub: repos, issues, PRs, Actions.
- GitLab: repos, merge requests, CI/CD.
- Atlassian: Jira, Confluence, Compass.
- Linear: issues and project tracking.
- Cloudflare: developer platform APIs.
- Vercel: projects, deployments, logs.
- Sentry: issues, events, releases.

## Key Repositories

- Official MCP servers repository: https://github.com/modelcontextprotocol/servers
  - Use this to study real MCP server implementations, available integrations, server configuration patterns, and examples of how tools/resources are exposed to AI clients.
- MCP GitHub organization: https://github.com/modelcontextprotocol

## Security Checklist

- Only connect MCP servers you trust.
- Prefer OAuth or environment variables over hardcoded tokens.
- Give tokens minimum scopes.
- Do not connect unrelated high-privilege MCP servers in the same session without a reason.
- Treat retrieved content as untrusted input.
- Require human approval before write actions.
- Review audit logs after agent actions.
