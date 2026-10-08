---
name: review-cycle-status
description: Check FeedbackPulse performance and peer review progress. Use when someone asks how a review cycle is going, which departments are behind, who has not started or is overdue, or wants a prep pack before calibration.
---

# Review Cycle Status

## When to Apply

Use when the user wants progress on a FeedbackPulse review cycle. Typical asks:

- "How is the Q1 review cycle going?"
- "Which departments are behind on reviews?"
- "Who on my team has not started their self review?"
- "Prep me for calibration on the H2 cycle."

## Who Can Use This

Admins see every review. Managers see their direct and indirect reports only. Employees get no review data through MCP. If a result looks short, check whether the user is a Manager before calling it a data problem.

## Tools

| Tool | Use it to | Notes |
|------|-----------|-------|
| `list_review_cycles` | Find cycles and their `review_cycle_id` | Includes completion stats for performance and peer reviews |
| `get_review_cycle_summary` | Get the department breakdown | Completed, in progress, not started and overdue counts. Needs `review_cycle_id` |
| `list_perf_reviews` | List each employee's performance review status | Defaults to the active cycle. Filters: `status` (completed, in_progress, not_started, overdue), `department`, `search`, `employee_id`. Needs performance reviews on the FeedbackPulse plan |
| `list_peer_reviews` | List peer reviews and their status | Filters: `review_cycle_id`, `status`. Anonymous reviewers stay hidden |
| `get_peer_review_stats` | Get peer review completion rate, average ratings and overdue count | Needs `review_cycle_id` |
| `list_employees` | Look up names, departments and managers | Filters: `status`, `department` (exact match), `search` |

The guided prompt `performance_review_prep` (arguments `review_cycle` required, `employee_name` optional) runs the calibration prep flow. It needs performance reviews on the FeedbackPulse plan.

## Steps

1. Call `list_review_cycles`. If the user did not name a cycle, use the active one and say which one you used.
2. Call `get_review_cycle_summary` for the department breakdown.
3. For "who is behind" questions, call `list_perf_reviews` with `status: overdue`, then `status: not_started`. Add `department` if the user named one.
4. For peer review questions, call `get_peer_review_stats`, then `list_peer_reviews` with a `status` filter if the user wants names.
5. Report back:
   - Cycle name and overall completion
   - Departments sorted from least to most complete, with overdue counts
   - Names of overdue people only when the user asked for names

## Rules

- If `list_perf_reviews` returns a plan error, tell the user performance reviews are not on their FeedbackPulse plan. Peer review and cycle tools still work.
- Never reveal anonymous peer reviewers. Do not guess them from timing or wording.
- Treat review status as a progress signal. Do not rank or judge people from status alone.
- This skill only reads data. Reminders and cycle changes happen in the FeedbackPulse dashboard.
