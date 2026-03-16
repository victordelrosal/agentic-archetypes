# /status

Quick snapshot of orders, open issues, active campaigns.

## Trigger

User says `/status` or "what's pending" or "how's the store"

## Flow

1. Note the current date.

2. Read .ops/state.json.

3. Surface three categories (only those with items):

   **Open tickets:**
   Customer issues with status "open".
   Show: customer, issue summary, age.

   **Active campaigns:**
   Campaigns with status "active" or "draft".
   Show: name, status, launch date.

   **Products pending:**
   Products with status "draft" (listings not yet published).
   Show: product name, next_action.

4. Format tight:
   "[N] open tickets. [N] active campaigns. [N] products
   pending." Then one line per item.

5. If clear: "Store is running clean. No pending items."

## Rules

- Under 10 lines.
- No resolved or archived items.
- No recommendations (that's /weekly-review).
- Read only.
- If empty: "No store ops tracked yet. Use /customer-reply
  or /new-product to get started."
