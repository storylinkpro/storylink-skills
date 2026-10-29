# storylink-skills

[![License: MIT](https://img.shields.io/badge/license-MIT-141412)](LICENSE)
[![Claude Code plugin](https://img.shields.io/badge/Claude%20Code-plugin-141412)](https://docs.claude.com/en/docs/claude-code/plugins)
[![MCP](https://img.shields.io/badge/MCP-storylink--mcp-141412)](https://github.com/storylinkpro/storylink-mcp)

This repository contains the agent skills for **[Storylink](https://storylink.pro)**. Storylink schedules and measures Instagram content (stories, feed posts and reels) for businesses and agencies.

The [Storylink MCP server](https://github.com/storylinkpro/storylink-mcp) gives an agent the tools to read your Instagram results. The skills tell the agent which tools to use, and in which sequence, for three tasks:

| Skill | What it does |
|---|---|
| `storylink-report` | It reads all your workspaces, or one workspace, and writes a weekly or monthly report. For each workspace, the report gives the totals and their change, and the best 3 and worst 3 items. It also gives the follower change and one thing to try next. |
| `storylink-investigate` | It finds when views dropped. It compares how often you posted, the mix of formats and the posting times before and after that day. Then it names the probable cause, or it says that there is no clear cause. |
| `storylink-whats-working` | It compares your best 10 and worst 10 items of the last 30 days. It looks for patterns in the type, the weekday, the hour and the caption length. Then it gives three concrete suggestions. |

> "Write my weekly Instagram report."
>
> "Why did my views drop this month?"
>
> "What works best on my Instagram, and what should I post more of?"

## Install in Claude Code

1. In Claude Code, add the marketplace and install the plugin:

   ```text
   /plugin marketplace add storylinkpro/storylink-skills
   /plugin install storylink@storylinkpro
   ```

2. Restart Claude Code.
3. Type `/mcp`, select `storylink` and sign in to Storylink. Allow access.

The plugin installs the three skills and the hosted Storylink MCP server (`https://storylink.pro/mcp`). The plugin does not ask for an API key. You sign in with your Storylink account, on any plan.

## Install in Cursor, Codex, Copilot and other agents

The skills use the open Agent Skills format (a `SKILL.md` file in a folder). Many agents can read them, for example Cursor, Codex, GitHub Copilot and Gemini CLI.

1. Add the Storylink MCP server to your agent. The [storylink-mcp README](https://github.com/storylinkpro/storylink-mcp#connect-with-sign-in-with-storylink) gives the configuration for claude.ai, Claude Desktop, Cursor, Windsurf and other clients.
2. Install the skills with the [skills CLI](https://github.com/vercel-labs/skills):

   ```bash
   npx skills add storylinkpro/storylink-skills
   ```

   The CLI asks which agents to install the skills for.

3. In the agent, ask: "Write my weekly Instagram report."

You can also copy a skill folder from `skills/` into the skills folder of your agent.

## Plans

The skills work on every Storylink plan. On the Free plan, the server shows the current month only. The numbers are always this month so far against last month. The skills tell you when the plan limited the numbers. Pro and Business show the full history.

## Security

- **The connection is read-only.** When you sign in with Storylink, the server gives the agent read tools only. The skills give advice. They cannot post, schedule or change content.
- **No key in your files.** The plugin uses Sign in with Storylink. The skills never write a token or a key into a file.
- **Data from outside.** Captions, comments, usernames and other text come from you, your clients and your audience. The skills tell the agent to use this text as data, never as instructions.
- **Limits.** Each signed-in user has 60 requests per minute. All the MCP clients of that user share this limit.
- **Disconnect an app.** In Storylink, open **Settings › Connected apps** and select **Revoke**. To use the app again, remove the Storylink connector in the app and add it again.

Send security problems to admin@storylink.pro.

## Links

- [Storylink](https://storylink.pro) · [storylink-mcp](https://github.com/storylinkpro/storylink-mcp) · [Privacy](https://storylink.pro/en/legal/privacy)
- [MIT License](LICENSE)
