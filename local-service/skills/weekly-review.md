# /weekly-review

Full business review: bookings, customers, marketing, operations.

## Trigger

User says `/weekly-review` or "how was my week" or "business review"

## Flow

1. Note the current date. Calculate this week and next week.

2. Read .ops/state.json completely.

3. Read .ops/log/ for session summaries from this week.

4. Compile four sections:

   **This week's activity:**
   Bookings completed, inquiries resolved, promotions run.
   If nothing: "Quiet week."

   **Open items:**
   Inquiries unanswered, bookings pending confirmation.
   Flag anything open longer than 24 hours.
   If nothing: "Nothing open."

   **Next week's schedule:**
   Confirmed bookings, promotion launches, follow-ups due.
   If nothing: "Next week is open."

   **Opportunities:**
   Slow days with no bookings, dormant customers (90+ days),
   reviews that need responses.
   If nothing: "No flags."

5. Present concise summary (under 15 lines).

6. End with a recommendation:
   "I'd suggest responding to [open inquiry] and [running
   a promotion for slow Tuesday slots]."

## Rules

- Never fabricate booking or revenue data.
- Read only. Don't change state.
- If empty: "No business ops tracked yet. Use /new-booking
  or /customer-reply to start."
