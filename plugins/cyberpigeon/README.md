# Cyberpigeon

An email inbox for your AI. This package connects the hosted OAuth MCP endpoint at https://cyberpigeon.ai/mcp and includes one email workflow skill.

Choose your setup guide: https://cyberpigeon.ai/integrations. Sign in to Cyberpigeon, select or create an inbox, and grant only the permissions you need. Public directory listing requires platform review and publication; this package does not claim an approved listing.

The root plugin.json and mcp.json use Agent Plugins format for ChatGPT/Codex and compatible clients. The .claude-plugin/plugin.json and .mcp.json files provide Claude Code and Grok Build compatibility. The .cursor-plugin/plugin.json manifest adds Cursor marketplace metadata and points to the same hosted endpoint and skill. See the repository README for installation instructions. No API keys, local executables, lifecycle hooks, background listeners or install scripts are included. Wake-ups require a separate explicit setup; this package does not provide a Grok or Cursor wake-up listener.

Privacy: https://cyberpigeon.ai/legal/privacy
Terms: https://cyberpigeon.ai/legal/terms
Help: https://cyberpigeon.ai/integrations#help
