# Parahuman for Cursor

Connect [Cursor](https://cursor.com) to your [Parahuman](https://parahuman.co) workspace. Parahuman is AI social listening: it ingests mentions of your brand, your competitors and any keyword you care about from across the social and developer web. This plugin puts that data in front of the agent.

## What's included

- **MCP server.** Connects to Parahuman's hosted MCP server at `https://api.parahuman.co/mcp/v1` over OAuth. No API key to paste.
- **Rules.** Guidance that keeps the agent honest about workspace scoping and about mention text being third party content rather than instructions.

## Platforms monitored

Reddit, X (Twitter), LinkedIn, YouTube, GitHub, Hacker News, Dev.to, Stack Overflow, Bluesky, newsletters and podcasts.

## Tools

| Tool | What it does | Scope |
|---|---|---|
| `list_workspaces` | List the workspaces this account can act on | `workspaces:read` |
| `get_workspace` | Name, slug, plan tier, read-only state | `workspaces:read` |
| `get_usage` | Plan limits and current consumption | `workspaces:read` |
| `list_mentions` | Search and page mentions, filtered by full text query, time window, keyword and read status | `mentions:read` |
| `get_mention_analytics` | Volume, sentiment and platform breakdown, with change against the prior period | `mentions:read` |
| `list_keywords` | The terms this workspace monitors | `keywords:read` |
| `create_keyword` | Start monitoring a term | `keywords:write` |
| `update_keyword` | Rename or re-describe a term | `keywords:write` |
| `set_keyword_paused` | Pause or resume monitoring | `keywords:write` |
| `delete_keyword` | Stop monitoring a term | `keywords:write` |
| `list_views` | Saved views with their filters, and whether each has an alert | `views:write` |
| `update_view` | Rename a saved view | `views:write` |
| `list_alerts` | Alerts, the view each one watches, and every destination | `views:write` |
| `create_alert` | Create the alert for a saved view, with email or Slack destinations and a frequency | `views:write` |
| `update_alert` | Rename, enable or disable an alert, or replace its destinations | `views:write` |
| `draft_reply` | Generate a reply to one mention and save it as a draft | `replies:draft` |

Sixteen tools in all. `draft_reply` never posts anything to the source platform. The draft is saved against the mention for a human to review and publish from the Parahuman dashboard.

## Authentication

Install the plugin, then run any Parahuman tool. Cursor opens a browser for a normal OAuth sign-in, then a consent screen listing every permission the agent wants, reads and writes together, so you can see up front that it is asking to manage keywords, manage saved views and alerts, and save reply drafts.

If you decline the write permissions, the read tools still work and the write tools are simply not offered to the agent. To grant a permission later, reconnect Parahuman from Cursor's MCP settings and approve it on the consent screen. Nothing writes to your workspace until you approve it.

Every tool other than `list_workspaces` takes an explicit `workspace` argument, so start by asking the agent to list your workspaces.

## Examples

Ask the agent things like:

- *"What did people say about us on Reddit this week?"*
- *"How did sentiment break down last month, and which platforms drove it?"*
- *"Has our mention volume moved against the previous period?"*
- *"Find every unread mention matching our competitor keyword"*
- *"Start monitoring the phrase 'social listening alternative'"*
- *"Draft a friendly reply to that Hacker News comment"*
- *"Send me a daily email digest of the 'competitor launches' view"*

## Disconnecting

**Settings, then AI agents** in the Parahuman dashboard. Disconnecting revokes the grant and stops tokens already issued to that client, so signing out of the dashboard alone is not enough.

## Requirements

A Parahuman account. MCP access is included on every plan, including the free trial.

## Links

- [Parahuman](https://parahuman.co)
- [MCP server guide](https://parahuman.co/docs/mcp)
- [Support](mailto:hello@parahuman.co)

## License

MIT
