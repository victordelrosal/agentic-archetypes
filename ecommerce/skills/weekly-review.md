# /weekly-review

Full business review: sales, customers, marketing, operations.

## Trigger

User says `/weekly-review` or "how was my week" or "business review"

## Flow

1. Note the current date. Calculate this week and next week.

2. Read .ops/state.json completely.

3. Read .ops/log/ for session summaries from this week.

4. Compile four sections:

   **Resolved this week:**
   Tickets closed, products listed, campaigns completed.
   If nothing: "Nothing closed this week."

   **Open issues:**
   Customer tickets still open, campaigns needing attention.
   Flag anything open longer than 48 hours.
   If nothing: "No open issues."

   **Coming next week:**
   Campaign launches, product deadlines, seasonal events.
   If nothing: "Nothing scheduled."

   **Inventory/Operations:**
   Any supplier tasks or operational flags.
   If nothing: "Operations running smooth."

5. Present concise summary (under 15 lines).

6. End with a recommendation:
   "I'd suggest resolving [oldest ticket] and reviewing
   [campaign] before it launches [date]."

## Rules

- Never fabricate activity or sales data.
- Read only. Don't change state.
- If empty: "No operations tracked yet. Use /customer-reply
  or /new-product to start."
