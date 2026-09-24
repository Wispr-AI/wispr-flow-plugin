# Wispr Flow MCP

The official Wispr Flow MCP server. Find meeting notes, transcripts, and calendar context from Wispr Flow in the AI
tools you already use.

Server URL: `https://api.wisprflow.ai/connect/mcp`. On first use you sign in with your existing Wispr Flow
account (OAuth). No API key needed.

## Install

| Tool | How |
| --- | --- |
| **Claude** | Add the [Wispr Flow connector](https://claude.ai/directory/connectors/wispr-flow) from the Claude connector directory |
| **ChatGPT** | Add the [Wispr Flow plugin](https://chatgpt.com/plugins/plugin_asdk_app_6a5ae9736be0819199d06d61ac171080?category=productivity&q=wispr) in ChatGPT |
| **Gemini** | Enable Wispr Flow in [Gemini Apps](https://gemini.google.com/apps) |
| **Cursor** | Install "Wispr Flow" from the Cursor plugin marketplace |
| **Grok Build** | Install "Wispr Flow" from the Grok Build plugin marketplace |
| **Claude Code** | `claude mcp add --transport http wispr-flow https://api.wisprflow.ai/connect/mcp` |
| **Any other MCP client** | Add the server URL above as a remote (HTTP) MCP server |

JSON config, for clients that take one:

```json
{
  "mcpServers": {
    "wispr-flow": {
      "type": "http",
      "url": "https://api.wisprflow.ai/connect/mcp"
    }
  }
}
```

This repository is the plugin package for marketplaces that install from Git (Cursor, Grok Build). It contains no
server code.

## Tools

Every tool is read-only. Tools return data from your own Wispr Flow account, plus notes that have been shared
with you through a Wispr Flow share link.

- **Meetings** — `search_meetings`, `get_meeting`, `get_meeting_by_calendar_id`, `list_meeting_series`,
  `list_upcoming_meetings`, `get_upcoming_meeting`, `resolve_share_link`
- **Notes** — `search_scratchpad_notes`, `get_scratchpad_note`
- **Calendar** — `search_calendar_events`, `get_calendar_event`, `resolve_calendar_link`
- **Account** — `get_account_info`
- **Contacts** (where available on your account) — `get_meeting_participants_enriched`, `get_participant_contacts`

## Requirements

- A Wispr Flow account
- Meeting recorder enabled in Wispr Flow for meeting notes and transcripts
- Enterprise accounts: your workspace admin must have the Wispr Flow MCP connector enabled (and Scratchpad access, for the notes tools)

## Support

- Help: https://wisprflow.ai/support or support@wisprflow.ai
- Privacy policy: https://wisprflow.ai/privacy-policy
- Terms of service: https://wisprflow.ai/terms-of-service
