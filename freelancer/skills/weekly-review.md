# /weekly-review

Full business review: what shipped, what's overdue, what's ahead.

## Trigger

User says `/weekly-review` or "how was my week" or
"what's the state of things"

## Flow

1. Note the current date. Calculate "this week" (Monday to
   Sunday containing today) and "next week."

2. Read .ops/state.json completely.

3. Read .ops/log/ for session summaries from this week.

4. Compile four sections:

   **Shipped this week:**
   Items moved to "completed" or "archived" this week.
   If nothing: "Nothing closed this week."

   **Overdue:**
   Items with due_date before today and status not
   "completed" or "archived". Flag each with how many
   days overdue.
   If nothing: "Nothing overdue."

   **Coming next week:**
   Items with due_date in the next 7 days.
   If nothing: "Next week is clear."

   **Stale leads:**
   Clients with type "client" or "followup" where
   updated_at is more than 14 days ago and status is
   still "active".
   If nothing: "No stale leads."

5. Present as a concise summary (not a data dump):
   "This week you closed [N] items: [list]. You have [N]
   overdue: [list]. Next week: [N] items due. [N] leads
   have gone cold."

6. End with a recommendation:
   "I'd suggest tackling [most urgent overdue item] first.
   Want me to draft a follow-up for [stale lead]?"

## Rules

- Never fabricate activity. If the logs are empty, say so.
- Keep the summary under 15 lines. Link to details, don't
  dump them.
- If state.json is empty or has very few entries, adjust
  tone: "Still early days. Here's where things stand."
- This is a review, not an action. Don't change state.
  Only surface information.
