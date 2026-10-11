# FeedbackPulse Survey Results, eNPS & Reviews

Ask Claude how your last employee engagement survey went, without opening a
dashboard. This plugin connects Claude (plus Cursor and Grok) to
[FeedbackPulse](https://feedbackpulse.com/integrations/claude), the employee
engagement software for growing teams. Your assistant can then read:

- survey results
- eNPS and how it has changed
- comment themes
- performance and peer review progress
- recognition
- employee data

Everything is scoped to what your role can see.

It's built for HR and People Ops leads, founders and managers who already run
FeedbackPulse. FeedbackPulse is free for teams of up to 10 people.

Need to design a new survey first? Use
[FeedbackPulse Employee Engagement Surveys & eNPS](../feedbackpulse-surveys-enps/README.md).

## Try it

- **Survey results:** "How did our last engagement survey go?"
- **eNPS:** "What is our eNPS and how did it change since last quarter?"
- **Comment themes:** "What themes came up in the comments on the Q3 pulse
  survey?"
- **Review progress:** "Which departments are behind on the Q1 review cycle?"
- **Overdue reviews:** "Who in Engineering has not started their performance
  review?"
- **Recognition:** "Who got the most kudos this quarter?"
- **Guided prompt:** "Run the engagement health check for Sales over the last
  90 days."

## What's included

- **MCP connection** to the FeedbackPulse server at
  `https://app.feedbackpulse.com/mcp`, with tools and guided prompts for
  surveys, reviews, recognition and employees.
- **Skills** for common workflows:
  - **Survey Results** reads survey scores, eNPS and its change since the last
    survey, low-scoring questions and comment themes.
  - **Review Cycle Status** checks performance and peer review progress by
    department and finds who is overdue.

The full tool list is in the
[MCP Tools Reference](https://feedbackpulse.com/help/integrations/mcp-tools-reference/).

## Before you start

An Admin has to turn on MCP for your organization:

1. In FeedbackPulse, go to **Settings > Features**.
2. Turn on **AI Integration** and click **Save**.
3. To give a Manager access, go to **Settings > Integrations** and turn on
   **MCP Access** for them. Admins have access by default.

Details: [Manage API tokens](https://feedbackpulse.com/help/integrations/token-management/).

## Install in Claude Code

```
/plugin marketplace add FeedbackPulseApp/feedbackpulse-plugin
/plugin install feedbackpulse@feedbackpulse
```

Run `/reload-plugins`, then `/mcp` to check that the FeedbackPulse server is listed.

For Claude.ai and Claude Desktop, see
[Connect Claude.ai](https://feedbackpulse.com/help/integrations/connect-claude-ai/).

## Install in Cursor or Grok Bot

Find **FeedbackPulse** in the [Cursor Marketplace](https://cursor.com/marketplace)
and install it. Grok Bot installs plugins from the same marketplace.

To test a local checkout first, link the plugin folder into Cursor's local
plugin folder:

```sh
mkdir -p ~/.cursor/plugins/local
ln -s /path/to/feedbackpulse-plugin/plugins/feedbackpulse ~/.cursor/plugins/local/feedbackpulse
```

Restart Cursor or run **Developer: Reload Window**. The FeedbackPulse skills and
MCP server should then show under **Customize**.

## Install in Grok Build

```
grok plugin marketplace add FeedbackPulseApp/feedbackpulse-plugin
grok plugin install feedbackpulse@feedbackpulse
```

## Sign-in and permissions

The first time the agent calls a FeedbackPulse tool, your browser opens and you
sign in with your FeedbackPulse account through OAuth. From then on, the plugin
acts as you and sees the same data your role sees in FeedbackPulse:

| Role | Surveys | Reviews | Recognition | Employees |
|------|---------|---------|-------------|-----------|
| Admin | All | All | All | All |
| Manager | None | Direct and indirect reports | None | Direct and indirect reports |
| Employee | None | None | None | None |

OAuth sign-in gives read access (`mcp:use`). Creating survey templates and
drafts needs the `mcp:write` scope, which only comes with a personal API token.
An Admin can create a token in **Settings > Integrations**, then connect with
this config instead:

```json
{
  "mcpServers": {
    "feedbackpulse": {
      "url": "https://app.feedbackpulse.com/mcp",
      "headers": {
        "Authorization": "Bearer YOUR_TOKEN"
      }
    }
  }
}
```

Keep the token out of shared files and repos.

Performance review and recognition tools only work if those features are on
your FeedbackPulse plan. If a feature is off, the tool returns an error and the
agent tells you.

## Privacy

The plugin sends requests to the FeedbackPulse MCP server at
`https://app.feedbackpulse.com/mcp`. Responses can include anything your
account can see, such as:

- employee names
- survey results
- review status
- recognition text

Anonymous survey comments are held back when a survey has fewer responses than
its privacy threshold. FeedbackPulse does not store your conversation content.

See the [privacy policy](https://feedbackpulse.com/privacy-policy) and
[terms of service](https://feedbackpulse.com/terms-of-service).

## Support

- [FeedbackPulse for Claude](https://feedbackpulse.com/integrations/claude)
- [MCP overview](https://feedbackpulse.com/help/integrations/mcp-overview/)
- [MCP troubleshooting](https://feedbackpulse.com/help/integrations/mcp-troubleshooting/)
- Email: support@feedbackpulse.com
