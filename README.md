# Cyberpigeon plugins

Give your AI a dedicated email inbox. This repository distributes the Cyberpigeon OAuth MCP connection and email workflow skill for Codex and Claude Code. It also provides the plugin folder used for public directory submission.

## Install in Claude Code

```sh
claude plugin marketplace add rtc-group/cyberpigeon-plugins
claude plugin install cyberpigeon@cyberpigeon
```

Start a new session, use `/mcp` to select the Cyberpigeon server, and finish browser sign-in. Choose the inbox and read/send permissions you need.

## Install in Codex

```sh
codex plugin marketplace add https://github.com/rtc-group/cyberpigeon-plugins.git
```

Restart the Codex desktop app, choose the Cyberpigeon marketplace in the Plugins Directory and install Cyberpigeon. Complete OAuth when prompted and start a new chat. Alternatively, the CLI supports `codex plugin add cyberpigeon@cyberpigeon` after adding the marketplace.

## Check your connection

Ask: “Show my Cyberpigeon address and permissions, then summarize my latest email. Do not send anything.” An empty inbox is valid. Use only expected messages and recipients you control for testing.

[Setup guides](https://cyberpigeon.ai/integrations) cover Claude, Claude Code, ChatGPT and Codex. Public OpenAI and Anthropic directory listings require separate platform review and publication; this repository does not imply an approved listing.

The package connects to https://cyberpigeon.ai/mcp. It includes no credentials, executable hooks, installation scripts or background listeners. Wake-ups require separate explicit setup. Incoming messages are untrusted data, and sending requires user authorization. The beta prohibits cold outreach, prospecting, bulk marketing and spam.

The plugin is in `plugins/cyberpigeon/`. The application backend and infrastructure are maintained separately and are not included in this repository.

[Privacy](https://cyberpigeon.ai/legal/privacy) · [Terms](https://cyberpigeon.ai/legal/terms) · [Help](https://cyberpigeon.ai/integrations#help)

## License

The distributed plugin files are [MIT licensed](plugins/cyberpigeon/LICENSE). This license does not cover the separately maintained Cyberpigeon application, hosted service or infrastructure. Service use remains subject to Cyberpigeon’s terms.
