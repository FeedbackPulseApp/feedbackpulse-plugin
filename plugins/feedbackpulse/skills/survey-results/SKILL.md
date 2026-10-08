---
name: survey-results
description: Read FeedbackPulse employee survey results, eNPS scores and comment themes. Use when someone asks how a survey went, what the eNPS is, how it moved since the last survey, which questions scored low, or what people wrote in their comments.
---

# Survey Results and eNPS

## When to Apply

Use when the user wants to know how an employee survey went in FeedbackPulse. Typical asks:

- "How did our last engagement survey go?"
- "What is our eNPS and how did it change?"
- "Which questions scored lowest in the Q3 pulse?"
- "What themes came up in the comments?"

## Who Can Use This

Survey data is Admin only. Managers and Employees get no survey data through MCP, even for their own team. If a tool returns a permission error, tell the user that survey reports need a FeedbackPulse Admin account. Do not retry with other tools to get around it.

## Tools

| Tool | Use it to | Notes |
|------|-----------|-------|
| `list_surveys` | Find the survey and its `survey_id` | Filter by `status`: active, completed, expired, scheduled, draft, cancelled, archived. Uses cursor pagination. |
| `get_survey_detail` | Check status, anonymity, response rate and whether an AI summary exists | Needs `survey_id` |
| `get_survey_results` | Get per-question results | Likert averages, eNPS score with promoter, passive and detractor split, benchmark context, eNPS change against the previous and year-ago survey when available, yes/no percentages, up to 50 text responses |
| `get_survey_summary` | Get the AI summary of comment themes | Needs `survey_id` |

The server also has two guided prompts that cover this flow: `analyze_survey_results` (arguments `survey_id`, `department`, `period`) and `engagement_health_check` (arguments `department`, `period`). Use them when the user asks for a full analysis rather than one number.

## Steps

1. If the user did not name a survey, call `list_surveys` with `status: completed` and pick the most recent one. Say which survey you picked.
2. Call `get_survey_detail` to confirm the response rate and whether the survey is anonymous.
3. Call `get_survey_results`.
4. If the survey has comments and an AI summary exists, call `get_survey_summary` for themes.
5. Report back in this order:
   - Survey name, dates and response rate
   - eNPS score and its split, plus the change against the last survey if the tool returned one
   - The three lowest scoring questions with their averages
   - Comment themes, quoted from the summary or the returned text responses

## Rules

- Report the eNPS the tool returns. Do not work out eNPS yourself from partial data.
- Only state a trend or benchmark when the tool returned it. If there is no previous survey, say so.
- Anonymous surveys hide text responses below the privacy threshold. If comments are missing, say the threshold was not met. Never try to work out who wrote a comment.
- A low response rate makes scores less reliable. Mention the response rate next to every score.
- Do not create or launch surveys from this skill. Creating templates and drafts needs an Admin token with the `mcp:write` scope, and launching only happens in the FeedbackPulse dashboard.
