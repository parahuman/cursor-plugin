# Changelog

## 1.0.0

First release.

- Remote MCP server at `https://api.parahuman.co/mcp/v1`, OAuth authenticated.
- Six read tools: workspaces, plan usage, mentions, mention analytics, keywords.
- Four keyword write tools, gated behind a separate `keywords:write` consent.
- `draft_reply`, which saves a draft for a human to publish and posts nothing.
- A rule covering workspace scoping and the handling of third party mention text.
