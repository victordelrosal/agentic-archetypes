# /customer-reply

Draft response to inquiry, complaint, or review.

## Trigger

User says `/customer-reply` or "reply to this review" or
"customer asked about..."

## Inputs

- **Message**: The customer's inquiry, complaint, or review
  (pasted or described)
- **Context**: Any service or booking history

## Flow

1. Delegate to **Customer Relations**
   (agents/customer-relations.md):
   - Categorize: inquiry, complaint, review response
   - Draft appropriate response
   - Save to workspace/reply-[customer].md

2. Create an inquiry entry in .ops/state.json:
   ```
   {
     id: "inquiry-[NNN]",
     type: "inquiry",
     customer: "[name]",
     service: "[relevant service or null]",
     status: "open",
     next_action: "review draft reply and send",
     due_date: [today],
     notes: "[issue type and summary]",
     updated_at: [now]
   }
   ```

3. Confirm to user:
   "Draft reply for [customer] is in workspace/.
   Type: [inquiry/complaint/review]. Review before sending."

## Rules

- Never send the reply. Draft only.
- Review responses should be crafted carefully; they're public.
- If resolution involves a refund or special accommodation,
  escalate.
