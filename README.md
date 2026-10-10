# FeedbackPulse plugin

This repo holds the [FeedbackPulse](https://feedbackpulse.com) plugin for [Cursor](https://cursor.com), [Grok](https://grok.com) and [Claude Code](https://claude.com/claude-code).

| Plugin | Use | Access |
| --- | --- | --- |
| [FeedbackPulse](./plugins/feedbackpulse/README.md) | Read survey results, eNPS, performance reviews, recognition and employee data | Authenticated FeedbackPulse account |
| [FeedbackPulse Surveys & eNPS](./plugins/feedbackpulse-surveys-enps/README.md) | Design and preview employee surveys, then optionally save the exact approved template or unlaunched draft | Anonymous preview; optional sign-in with `survey-design:persist` for saving |

Each plugin's README covers install, sign-in, usage and privacy. In Claude Code, add this marketplace with `/plugin marketplace add FeedbackPulseApp/feedbackpulse-plugin`, then install the survey designer with `/plugin install feedbackpulse-surveys-enps@feedbackpulse`.

FeedbackPulse Surveys & eNPS uses its own [proprietary license](./plugins/feedbackpulse-surveys-enps/LICENSE), which permits authorized official marketplace distribution. The repository's MIT license applies to the existing FeedbackPulse plugin and marketplace files.

For the full MCP docs, including Claude Desktop and Claude.ai setup, see [feedbackpulse.com/help/integrations/mcp-overview](https://feedbackpulse.com/help/integrations/mcp-overview/).
