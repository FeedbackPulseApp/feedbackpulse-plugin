# FeedbackPulse plugins for Claude, Cursor and Grok

This repo holds the [FeedbackPulse](https://feedbackpulse.com/integrations/claude)
plugins for employee engagement surveys, pulse surveys and eNPS. Use them to
design a survey in your AI assistant, or to ask about the results of surveys
you've already run.

| Plugin | What it does | Account needed | Where |
| --- | --- | --- | --- |
| [FeedbackPulse Employee Engagement Surveys & eNPS](./plugins/feedbackpulse-surveys-enps/README.md) | Design and refine employee engagement, pulse and eNPS surveys, then optionally save the approved survey as a template or unlaunched draft | None to design. A FeedbackPulse admin account to save | Claude |
| [FeedbackPulse Survey Results, eNPS & Reviews](./plugins/feedbackpulse/README.md) | Read survey results, eNPS trends, comment themes, performance review progress and recognition | A FeedbackPulse account | Claude, Cursor, Grok |

## Install in Claude Code

```
/plugin marketplace add FeedbackPulseApp/feedbackpulse-plugin
/plugin install feedbackpulse-surveys-enps@feedbackpulse
/plugin install feedbackpulse@feedbackpulse
```

Each plugin's README covers sign-in, examples and privacy. For Claude Desktop
and Claude.ai setup, see the
[FeedbackPulse MCP docs](https://feedbackpulse.com/help/integrations/mcp-overview/).

## About FeedbackPulse

FeedbackPulse is employee engagement software for growing teams. It covers:

- pulse surveys
- eNPS
- anonymous engagement surveys
- 360 feedback
- performance reviews
- recognition

It's free for teams of up to 10 people. Learn more at
[feedbackpulse.com](https://feedbackpulse.com).

## License

FeedbackPulse Employee Engagement Surveys & eNPS uses its own
[proprietary license](./plugins/feedbackpulse-surveys-enps/LICENSE), which
permits authorized official marketplace distribution. The repository's MIT
license applies to the FeedbackPulse Survey Results, eNPS & Reviews plugin and
the marketplace files.
