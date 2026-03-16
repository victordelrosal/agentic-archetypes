# /status

Quick snapshot of today's bookings, open inquiries, active promos.

## Trigger

User says `/status` or "what's the schedule" or "what's pending"

## Flow

1. Note the current date.

2. Read .ops/state.json.

3. Surface three categories (only those with items):

   **Today's bookings:**
   Bookings with due_date of today.
   Show: customer, service, time.

   **Open inquiries:**
   Inquiries with status "open".
   Show: customer, issue, age.

   **Active promotions:**
   Promotions with status "active".
   Show: name, end date.

4. Format tight:
   "[N] bookings today. [N] inquiries open. [N] promos
   running." Then one line per item.

5. If clear: "Schedule is clear. No pending items."

## Rules

- Under 10 lines.
- No completed or archived items.
- No recommendations (that's /weekly-review).
- Read only.
- If empty: "No business ops tracked yet. Use /new-booking
  to get started."
