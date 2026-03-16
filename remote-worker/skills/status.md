# /status

Quick daily snapshot of tasks and deadlines.

## Trigger

User says `/status` or "what's on my plate" or "what's pending"

## Flow

1. Note the current date.

2. Read .ops/state.json.

3. Surface three categories (only those with items):

   **Due today/tomorrow:**
   Tasks, meetings, documents due in the next 48 hours.
   Show: project, next_action, due_date.

   **In progress:**
   Items with status "active" or "draft".
   Show: project, next_action.

   **Overdue:**
   Items past due_date, not completed.
   Show: project, how many days overdue.

4. Format tight:
   "[N] due soon. [N] in progress. [N] overdue."
   Then one line per item.

5. If clear: "All clear. No pending items."

## Rules

- Under 10 lines.
- No completed or archived items.
- No recommendations (that's /weekly-review).
- Read only.
- If empty: "No work tracked yet. Start with /triage or
  /prep to seed your operations."
