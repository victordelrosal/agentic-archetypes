# /status

Quick daily snapshot of where things stand.

## Trigger

User says `/status` or "what's pending" or "where are we"

## Flow

1. Note the current date.

2. Read .ops/state.json.

3. Surface three categories (only those with items):

   **Active projects:**
   Items with type "project" and status "active".
   Show: client, next_action, due_date.

   **Pending proposals:**
   Items with type "proposal" and status "draft" or
   "pending". Show: client, due_date.

   **Overdue follow-ups:**
   Items with type "followup" and due_date before today.
   Show: client, how many days overdue.

4. Format as a tight summary:
   "[N] active projects. [N] proposals pending.
   [N] follow-ups overdue."
   Then list each with one line per item.

5. If everything is clear:
   "All clear. No pending items."

## Rules

- This is the lightweight daily check. Keep it under 10
  lines total.
- Don't include completed or archived items.
- Don't make recommendations (that's /weekly-review).
- Don't modify state. Read only.
- If state.json doesn't exist or is empty:
  "No operations set up yet. Run through the onboarding
  first, or use /new-lead to get started."
