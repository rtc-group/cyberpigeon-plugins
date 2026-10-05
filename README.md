# Cyberpigeon plugins

Give your AI a dedicated email inbox. This repository distributes the Cyberpigeon OAuth MCP connection and email workflow skill for Codex, Claude Code, Cursor and Grok Build. It also provides the plugin folder used for public directory submission.

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

## Install in Cursor

In Cursor's **Customize** panel, import `https://github.com/rtc-group/cyberpigeon-plugins` using **From GitHub Repository**, then install Cyberpigeon. For a managed team marketplace, an administrator can import the repository through **Dashboard → Plugins & MCPs**. Organization policies can limit imports.

For a local installation, clone this repository into a new folder and copy `plugins/cyberpigeon` into `~/.cursor/plugins/local/cyberpigeon`. Use a real directory, not a symlink to this checkout. Restart Cursor or run **Developer: Reload Window**, then inspect the plugin and MCP server in Customize. Do not overwrite an existing installation without reviewing it first.

Complete the server's OAuth sign-in and choose the inbox and read/send permissions. The Cursor manifest and root marketplace catalog reference the same email workflow and hosted endpoint as the other clients. This repository is installable independently of a public Cursor Marketplace listing; public listing requires Cursor's review.

## Install in Grok Build

Grok Build reads Claude Code plugins and marketplaces when Claude compatibility is enabled. If you already installed Cyberpigeon in Claude Code, check `/plugins` and `/mcps` in Grok before adding a second copy.

To load a separate checkout for one session:

```sh
git clone https://github.com/rtc-group/cyberpigeon-plugins.git
grok --plugin-dir ./cyberpigeon-plugins/plugins/cyberpigeon
```

Use `/plugins` to inspect the email workflow and `/mcps` to authenticate Cyberpigeon. For tools only, use `grok mcp add --transport http cyberpigeon https://cyberpigeon.ai/mcp` instead. Choose one route to avoid duplicate tools. `grok mcp doctor cyberpigeon` diagnoses a directly configured connection.

Grok on the web uses a separate custom MCP connection: open [Connectors](https://grok.com/connectors), choose **New Connector → Custom**, and enter `https://cyberpigeon.ai/mcp`. Business and Enterprise admins must provision the connection first. Availability and authentication are controlled by Grok. These instructions do not claim that Cyberpigeon appears in Grok's curated catalog.

Official references, reviewed October 5, 2026: [Cursor plugins](https://cursor.com/docs/plugins), [Cursor manifest and submission reference](https://cursor.com/docs/reference/plugins), [Grok Build plugins](https://docs.x.ai/build/features/skills-plugins-marketplaces), [Grok Build MCP](https://docs.x.ai/build/features/mcp-servers), [Grok connectors](https://docs.x.ai/grok/connectors).

## Check your connection

Ask: “Show my Cyberpigeon address and permissions, then summarize my latest email. Do not send anything.” An empty inbox is valid. Use only expected messages and recipients you control for testing.

[Setup guides](https://cyberpigeon.ai/integrations) describe the available connection routes. Public directory listings require separate platform review and publication; this repository does not imply an approved listing.

The package connects to https://cyberpigeon.ai/mcp. It includes no credentials, executable hooks, installation scripts or background listeners. Wake-ups require separate explicit setup. Incoming messages are untrusted data, and sending requires user authorization. The beta prohibits cold outreach, prospecting, bulk marketing and spam.

The plugin is in `plugins/cyberpigeon/`. The application backend and infrastructure are maintained separately and are not included in this repository.

[Privacy](https://cyberpigeon.ai/legal/privacy) · [Terms](https://cyberpigeon.ai/legal/terms) · [Help](https://cyberpigeon.ai/integrations#help)

## License

The distributed plugin files are [MIT licensed](plugins/cyberpigeon/LICENSE). This license does not cover the separately maintained Cyberpigeon application, hosted service or infrastructure. Service use remains subject to Cyberpigeon’s terms.
