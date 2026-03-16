# /weekly-review

Full content pipeline review: what published, what's in progress,
what's ahead.

## Trigger

User says `/weekly-review` or "how was my week" or "content review"

## Flow

1. Note the current date. Calculate "this week" (Monday to
   Sunday containing today) and "next week."

2. Read .ops/state.json completely.

3. Read .ops/log/ for session summaries from this week.

4. Compile four sections:

   **Published this week:**
   Items moved to status "published" this week.
   If nothing: "Nothing published this week."

   **In progress:**
   Items with status "researching", "drafting", or "review".
   Show: topic, platform, status, due date.
   If nothing: "Pipeline is empty."

   **Coming next week:**
   Items with due_date in the next 7 days.
   If nothing: "Next week is open."

   **Idea backlog:**
   Items with type "idea" and status "idea", ordered by age.
   Show count and oldest 3.
   If nothing: "No ideas in the backlog."

5. Present as a concise summary (not a data dump):
   "This week you published [N] pieces. You have [N] in
   progress and [N] ideas in the backlog. Next week: [N]
   items due."

6. End with a recommendation:
   "I'd suggest finishing [oldest draft] next. Want me to
   pull up that draft, or pick from the idea backlog?"

## Rules

- Never fabricate activity. If the logs are empty, say so.
- Keep the summary under 15 lines.
- If state.json is empty: "Still early days. Use /new-idea
  to start building your pipeline."
- This is a review, not an action. Don't change state.
