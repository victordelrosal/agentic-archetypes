# /weekly-review

Full work review: what shipped, what's pending, what's next.

## Trigger

User says `/weekly-review` or "how was my week" or "weekly review"

## Flow

1. Note the current date. Calculate this week and next week.

2. Read .ops/state.json completely.

3. Read .ops/log/ for session summaries from this week.

4. Compile four sections:

   **Completed this week:**
   Items moved to "completed" or "archived" this week.
   If nothing: "Nothing closed this week."

   **Overdue:**
   Items with due_date before today and status not
   "completed" or "archived". Flag how many days overdue.
   If nothing: "Nothing overdue."

   **Coming next week:**
   Items with due_date in the next 7 days, plus any
   meetings scheduled.
   If nothing: "Next week is clear."

   **Stale items:**
   Tasks or documents with updated_at older than 14 days
   and status still "active" or "pending".
   If nothing: "No stale items."

5. Present concise summary (under 15 lines).

6. End with a recommendation:
   "I'd suggest tackling [most urgent overdue item] first.
   Want me to prep for [upcoming meeting]?"

## Rules

- Never fabricate activity.
- This is read-only. Don't change state.
- If state is empty: "No work tracked yet. Use /triage or
  /prep to start building your operations."
