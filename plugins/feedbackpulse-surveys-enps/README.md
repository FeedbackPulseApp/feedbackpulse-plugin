# Employee surveys by FeedbackPulse

Design and refine a complete English employee survey before connecting an
account. Choose 1–100 questions for a short pulse, engagement survey, or eNPS
survey. Broad engagement work usually benefits from 8–12 questions; explicit
counts take priority and eNPS is optional.

## Connect and use

Enable the `design-employee-survey` skill in your assistant. Try: “Design exactly
three questions about role clarity after a reorganization. Do not include eNPS.”
Or: “Create an eNPS pulse with one optional comment.”

The assistant shows the privacy notice before sending your brief to FeedbackPulse,
asks for missing context, then presents every question and an estimated completion
time. Refine, keep, or export the design without an account. After approving the
whole survey, choose a reusable template or an unlaunched draft. Saving requires
an eligible FeedbackPulse admin and only `survey-design:persist` permission.
Cancelling sign-in leaves the design available.

ChatGPT/Codex uses the packaged app connection and the existing
`https://app.feedbackpulse.com/mcp/employee-surveys` service. The Claude package
references `https://app.feedbackpulse.com/mcp/employee-surveys/claude`. Both use contract 2026-10-10.2: preview_survey, prepare_survey_save, save_survey. Deployment and host verification are separate release steps. Before distributing the Claude package, its publisher must verify
that endpoint, OAuth, and installation in the intended Claude clients. In Claude,
the plugin and connector must use the same URL. An organization owner may need
to enable the connector.

## Data and permissions

The package contains a skill, static assets, and a remote service reference. It
runs no local programs, hooks, installers, or model API calls. Proposal context
and proposed questions needed for design are sent to FeedbackPulse. Do not
include employee names, individual allegations, credentials, health records,
or other restricted personal information. Ordinary design inputs are retained
for up to 90 days to provide and improve the service. Designs expire; keep or
export the final version if needed.

Saving creates the exact approved template, or a template plus a zero-recipient,
unscheduled draft. It never launches, schedules, adds recipients, sends invitations
or reminders, collects responses, or reads results. Finish operational setup in
FeedbackPulse through the returned review link.

## Support and terms

- [FeedbackPulse](https://feedbackpulse.com/)
- [Support](https://feedbackpulse.com/support)
- [Privacy policy](https://feedbackpulse.com/privacy-policy)
- [Terms of service](https://feedbackpulse.com/terms-of-service)

See `LICENSE` for permitted use. FeedbackPulse publishes this plugin; it is not
an OpenAI or Anthropic product.

Old intake tools/references and pending receipts are retired. Refresh tools or reconnect, then submit a fresh complete proposal; review and approve again. Keep/export remains available without an account.
