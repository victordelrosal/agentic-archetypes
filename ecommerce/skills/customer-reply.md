# /customer-reply

Draft a response to a customer inquiry or complaint.

## Trigger

User says `/customer-reply` or "customer asked about..." or
"handle this complaint"

## Inputs

- **Customer message**: The inquiry or complaint (pasted or described)
- **Context**: Any relevant order or product info

## Flow

1. Delegate to **Customer Service**
   (agents/customer-service.md):
   - Categorize the issue
   - Draft a response following store policies
   - Save draft to workspace/reply-[customer].md

2. Create a ticket entry in .ops/state.json:
   ```
   {
     id: "ticket-[NNN]",
     type: "ticket",
     customer: "[name]",
     product: "[product if relevant]",
     status: "open",
     next_action: "review draft reply and send",
     due_date: [today],
     notes: "[issue summary]",
     updated_at: [now]
   }
   ```

3. Confirm to user:
   "Draft reply for [customer] is in workspace/.
   Issue: [category]. Review before sending."

## Rules

- Never send the reply. Draft only.
- If resolution requires a refund or exception, escalate.
- Response time matters: flag if this is a repeat inquiry.
