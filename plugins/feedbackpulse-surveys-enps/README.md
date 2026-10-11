# FeedbackPulse Employee Engagement Surveys & eNPS

Design employee engagement surveys, pulse surveys and eNPS surveys in Claude.
Describe what you need to learn about your team, review every question, and
refine the survey until it fits. You don't need an account to design. When the
survey is ready, you can save the approved version to
[FeedbackPulse](https://feedbackpulse.com/integrations/claude) as a reusable
survey template or an unlaunched draft.

It's built for HR leaders, People Operations teams and HR managers planning an
employee listening program. Founders and HR consultants who need good survey
questions fast can use it too.

## What you can design

- **Employee engagement surveys.** Broad surveys covering engagement, trust in
  leadership, growth, workload and belonging. Broad engagement surveys usually
  work best with 8 to 12 questions.
- **Pulse surveys.** Short check-ins on one topic, such as role clarity after a
  reorganization or workload during a busy quarter.
- **eNPS surveys.** The Employee Net Promoter Score question ("How likely are
  you to recommend working here?") on a 0 to 10 scale. Use it on its own or
  alongside other questions. eNPS is always optional.
- **Any length from 1 to 100 questions.** Mix 5-point scales, eNPS, yes/no and
  open-text questions. If you ask for an exact count, Claude uses it.

Every design comes back with:

- an estimated completion time
- privacy and anonymity guidance
- the assumptions Claude made, so you can correct them

## Try it

- "Design a 10-question employee engagement survey for our 120-person software
  company. We reorganized last quarter and want to understand trust in
  leadership and retention risk."
- "Create a 5-question monthly pulse survey for a remote customer support team,
  with eNPS and one optional comment."
- "Design exactly three questions about role clarity after a reorganization.
  Do not include eNPS."
- "Build an eNPS survey with one follow-up question asking why people chose
  their score."
- "This feels too generic. We're six weeks into a reorganization. Rewrite the
  survey around change clarity and keep it under five minutes."

## How it works

1. **Describe what you need.** Claude shows a short privacy notice first. It
   then asks for anything missing: your goal, who will take the survey, how
   you'll use the results and how sensitive the topic is.
2. **Review the complete survey.** You see every question with its answer
   scale and whether it's required, plus the estimated completion time.
3. **Refine it.** Say what isn't working and Claude returns a complete updated
   version.
4. **Approve it, then choose what happens next:**
   - keep or export it, with no account
   - save it to FeedbackPulse as a reusable survey template
   - save it as a survey draft (the template plus an unlaunched setup)

## What it doesn't do

This plugin designs surveys. It doesn't do any of the following:

- launch or schedule surveys
- add respondents
- send invitations or reminders
- collect responses
- analyze results or provide benchmarks

You finish setup and launch in FeedbackPulse, using the review link Claude
gives you after saving.

Already running surveys in FeedbackPulse? Use
[FeedbackPulse Survey Results, eNPS & Reviews](../feedbackpulse/README.md) to
ask Claude about your results.

Designing without an account is not the same as running an anonymous survey.
Anonymity is set up when you launch the survey in FeedbackPulse.

## Install

**Claude Code**

```
/plugin marketplace add FeedbackPulseApp/feedbackpulse-plugin
/plugin install feedbackpulse-surveys-enps@feedbackpulse
```

**Claude.ai and Claude Desktop:** [download the survey designer plugin](https://feedbackpulse.com/assets/integrations/feedbackpulse-surveys-enps-1.1.0.zip)
and upload it under Customize > Plugins. Until the directory listing is available,
add a custom connector at `https://app.feedbackpulse.com/mcp/employee-surveys/claude`
with sign-in only when needed and automatic OAuth registration. Once listed,
install this plugin from the Claude directory. On Team and Enterprise plans, an
organization owner may need to enable it first. The plugin and connector must
use the same service URL.

## Saving to FeedbackPulse

Saving is optional. It requires an eligible FeedbackPulse admin account and asks
only for the `survey-design:persist` permission. If you cancel sign-in, your
design stays available to keep or export.

Saving creates exactly the survey you approved. You get either a template, or a
template plus a draft. The draft has no recipients and no schedule, and it sends
no notifications. It opens in FeedbackPulse at Basic Info, then Reminders,
Respondents, Scheduling and Review.

FeedbackPulse is employee engagement software for growing teams. It covers
pulse surveys, eNPS, engagement surveys, 360 feedback and performance reviews.
It's free for teams of up to 10 people.

## Data and privacy

- Your proposal context and the questions needed for the design are sent to
  FeedbackPulse.
- Don't include any of the following:
  - employee names
  - individual allegations
  - credentials
  - health records
  - other restricted personal information
- Ordinary design inputs are kept for up to 90 days to provide and improve the
  service.
- Survey design is currently available in English.
- Designs expire, so keep or export your final version if you need it.

The package contains a skill, static assets and a remote service reference. It
runs no local programs, hooks, installers or model API calls.

## Technical details

- **Service:** `https://app.feedbackpulse.com/mcp/employee-surveys/claude`
- **Contract:** 2026-10-10.2
- **Tools:**
  - `preview_survey`
  - `prepare_survey_save`
  - `save_survey`

The same survey designer is also available as a ChatGPT app.

**Troubleshooting:** older intake tools and pending save receipts have been
retired. If Claude still lists them, refresh tools or reconnect. Then submit a
fresh complete design and approve it again. Keep or export remains available
without an account.

## Support and terms

- [FeedbackPulse for Claude](https://feedbackpulse.com/integrations/claude)
- [Support](https://feedbackpulse.com/support)
- [Privacy policy](https://feedbackpulse.com/privacy-policy)
- [Terms of service](https://feedbackpulse.com/terms-of-service)

See `LICENSE` for permitted use. FeedbackPulse publishes this plugin. It is not
an Anthropic product.
