---
name: design-employee-survey
description: Design an English employee engagement, pulse or eNPS survey without an account, review and refine every question, then optionally save the approved survey to FeedbackPulse as a template or unlaunched draft.
---

# Design an employee survey

## Conversation before connecting

No account or OAuth is needed to design, preview, refine, keep or export. Never ask
for connection until the user chooses to save. Do not use broad FeedbackPulse tools.

Show the notice verbatim and obtain explicit acceptance before preview_survey:
“Do not include employee names or specific allegations. Ordinary design inputs are
retained for up to 90 days to provide and improve the service. Survey design is
currently supported in English.”

Reflect known context. Ask one decision-changing question at a time, using numbered
options and allowing free text. Gather goal, audience, intended_use and sensitivity.
Do not invent these facts. If unknown, ask the user to explicitly choose a stated
assumption. Optional context includes company_size, known_challenges, cultural_values,
recent_changes, anonymity_needs and ability_to_act. Keep conversational intake in this
skill; the server has no readiness score, next question or conversation recovery.

## Complete validated preview

Compose the complete proposal with name, template_type, purpose, description,
introduction, depth and questions. Each question has question, type, is_required and
appropriate options: likert uses label_preset or exactly five custom_labels; enps uses
low_label and high_label; yes_no and text omit options. Use only supported formats.
Recommend 8–12 for broad engagement; honor explicit 1–100 counts and short pulses
without padding or forced eNPS. Focused permits at most two text questions. Do not
promise benchmark lookup, launch, recipients, invitations, reminders or reporting.

Call preview_survey with disclosure_accepted=true, the complete context and proposal.
The server may normalize wording, eNPS and privacy guidance. Review its canonical
artifact, not your original proposal. Begin with a decision brief: purpose, audience,
question count, estimated minutes, privacy caveats and assumptions. Show the whole
survey, every question, type, labels and required state.

If rejected, ask “What did not work?” with numbered reasons. Summarize what changed.
Submit a complete replacement to preview_survey with the same design_reference and
current design_version, context, disclosure acceptance and optional rejection_reason.
Revisions invalidate pending approvals. On proposal_invalid correct and resubmit;
you must not call persistence with a failed proposal. On safety_stopped remove
restricted content and start with a fresh complete proposal. Follow safe_fallback.
Expired/lost/stale references require complete resubmission, review and approval.

## Explicit approval and optional saving

After the user explicitly approves every question in the canonical preview, offer:

1. just create a template, reusable for later;
2. create a survey draft, the template plus an unlaunched setup;
3. Keep or export it, with no account or connection.

For choices 1 or 2 call prepare_survey_save with the exact design_reference,
design_version, approved=true and persistence_choice=template or draft. Never
synthesize a receipt or change its action. Preparation creates no tenant resources.

Call save_survey with that receipt. If challenged, connect through the host OAuth
flow with survey-design:persist, then retry the unchanged receipt. Cancellation
leaves the design available for export; never claim it was saved. Duplicate saves
with the same authorized actor return the same resource. Refreshed/reconnected
credentials still require the same eligible admin and tenant for replay. For an
expired receipt prepare again after re-reviewing a valid preview; if the preview
expired, resubmit the complete proposal first.

Only claim saved when persistence.confirmed=true. Show the handoff_url verbatim.
The draft opens Basic Info → Reminders → Respondents → Scheduling → Review/Launch.
It has zero recipients, no schedule and sends no notifications. Setup and launch
remain in FeedbackPulse. Do not invent links, resource IDs or successful writes.

## Contract reset

This is contract/capability 2026-10-10.2. Exactly three workflow tools. Old intake
tools, conversations and pending receipts are retired. Refresh tools/reconnect
if the host still advertises them, then submit a fresh complete proposal. Do not
translate or restore legacy pending approvals. Historical snapshots are records.
