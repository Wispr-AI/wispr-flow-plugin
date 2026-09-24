# Wispr Flow plugin

Find meeting notes, transcripts, and calendar context from Wispr Flow inside your AI coding assistant.

The plugin connects your assistant to the Wispr Flow remote MCP server (`https://api.wisprflow.ai/connect/mcp`).
On first use you sign in with your existing Wispr Flow account (OAuth).

## Tools

Every tool is read-only. Tools return data from your own Wispr Flow account, plus notes that have been shared
with you through a Wispr Flow share link.

- **Meetings** — `search_meetings`, `get_meeting`, `get_meeting_attendee_emails`, `get_meeting_by_calendar_id`,
  `list_meeting_series`, `list_upcoming_meetings`, `get_upcoming_meeting`, `resolve_share_link`
- **Notes** — `search_scratchpad_notes`, `get_scratchpad_note`
- **Calendar** — `search_calendar_events`, `get_calendar_event`, `resolve_calendar_link`
- **Account** — `get_account_info`

## Install

**Cursor** — search for "Wispr Flow" in the Cursor plugin marketplace, or install from this repository.

**Grok Build** — search for "Wispr Flow" in the Grok Build plugin marketplace.

**Claude Code / other MCP clients** — add the server directly:

```bash
claude mcp add --transport http wispr-flow https://api.wisprflow.ai/connect/mcp
```

or in a JSON MCP config:

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

## Requirements

- A Wispr Flow account
- Meeting recorder enabled in Wispr Flow for meeting notes and transcripts
- Enterprise accounts: your workspace admin must have the Wispr Flow MCP connector enabled (and Scratchpad access, for the notes tools)

## Support

- Help: https://wisprflow.ai/support or support@wisprflow.ai
- Privacy policy: https://wisprflow.ai/privacy-policy
- Terms of service: https://wisprflow.ai/terms-of-service
