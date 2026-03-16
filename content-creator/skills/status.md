# /status

Quick daily snapshot of the content pipeline.

## Trigger

User says `/status` or "what's pending" or "where are we"

## Flow

1. Note the current date.

2. Read .ops/state.json.

3. Surface three categories (only those with items):

   **Due soon:**
   Items with due_date within the next 3 days.
   Show: topic, platform, status, due date.

   **In progress:**
   Items with status "researching", "drafting", or "review".
   Show: topic, platform, next_action.

   **Overdue:**
   Items with due_date before today and status not
   "published" or "archived".
   Show: topic, how many days overdue.

4. Format as a tight summary:
   "[N] due this week. [N] in progress. [N] overdue."
   Then list each with one line per item.

5. If everything is clear:
   "Pipeline is clear. No pending items."

## Rules

- Keep it under 10 lines total.
- Don't include published or archived items.
- Don't make recommendations (that's /weekly-review).
- Don't modify state. Read only.
- If state.json doesn't exist or is empty:
  "No content pipeline set up yet. Run through the
  onboarding first, or use /new-idea to get started."
