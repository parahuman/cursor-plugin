# Changelog

## 1.0.0

First release.

- Remote MCP server at `https://api.parahuman.co/mcp/v1`, OAuth authenticated.
- Six read tools: workspaces, plan usage, mentions, mention analytics, keywords.
- Four keyword write tools under `keywords:write`.
- Five saved view and alert tools under `views:write`: list and rename views, list, create and update alerts.
- `draft_reply` under `replies:draft`, which saves a draft for a human to publish and posts nothing.
- One consent screen listing reads and writes together. Declining the writes leaves every read tool working.
- A rule covering workspace scoping, alert destinations, and the handling of third party mention text.
