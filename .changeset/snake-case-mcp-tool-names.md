---
'@backstage/plugin-mcp-actions-backend': minor
---

MCP tool names are now normalized to `snake_case` before they are exposed. The plugin ID separator and any hyphens in plugin IDs or action names are replaced with underscores, so an action such as `greet-user` from `my-custom-plugin` is now listed as `my_custom_plugin_greet_user`. This fixes tool calling for LLM clients (such as Anthropic Claude and Google Gemini) that reject tool names containing `.` or `-`.

Tool calls that reference the previous, un-normalized name (for example `my-custom-plugin.greet-user`) continue to resolve, so existing clients keep working without changes.
