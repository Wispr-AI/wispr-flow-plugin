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

## What you can do

Ask your AI about your Wispr Flow data, for example:

- "What did we decide in yesterday's pricing meeting?"
- "Summarize my calls with Acme this month and list open action items."
- "Prep me for my next meeting."
- "Find my scratchpad note on the hiring plan."

The server can search and read your meetings and transcripts, scratchpad notes, and calendar events, plus notes
shared with you through a Wispr Flow share link. Access is read-only: it never creates, edits, or deletes anything.

## Requirements

- A Wispr Flow account
- Notetaker with Cloud Sync turned on, for meeting notes and transcripts
- Enterprise accounts: your workspace admin must have the Wispr Flow MCP connector enabled (and Scratchpad access, for the notes tools)
- Not available for HIPAA-covered accounts

## Support

- Help: https://wisprflow.ai/support or support@wisprflow.ai
- Privacy policy: https://wisprflow.ai/privacy-policy
- Terms of service: https://wisprflow.ai/terms-of-service
