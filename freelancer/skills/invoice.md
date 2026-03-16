# /invoice

Generate an invoice for a client project.

## Trigger

User says `/invoice` or "invoice [client] for..."

## Inputs

- **Client name**: Who to invoice
- **Project or description**: What the invoice is for
- **Amount**: (optional) If not provided, calculate from
  config.yaml rates and project scope

## Flow

1. Look up the client in .ops/state.json. If not found:
   "I don't have [name] in the system. Want me to add
   them first?"

2. Pull business details and rates from config.yaml:
   - Business name, owner, location
   - Rates (hourly/day/project)
   - Payment terms
   - Payment methods

3. Delegate to **Admin Assistant** (agents/admin-assistant.md):
   - Generate invoice using templates/invoice-template.md
   - Auto-increment invoice number from .ops/state.json
     (find the highest existing invoice id, add 1)
   - Output to workspace/invoice-[client]-[number].md

4. Create an invoice entry in .ops/state.json:
   ```
   {
     id: "inv-[NNN]",
     type: "invoice",
     client: "[name]",
     status: "draft",
     next_action: "review and send to client",
     due_date: [today],
     updated_at: [now]
   }
   ```

5. Confirm to user:
   "Invoice #[NNN] for [client] is in workspace/.
   Total: [amount]. Payment terms: [terms from config].
   Review before sending."

## Rules

- Never invent an amount. If the user doesn't specify and
  the project scope isn't clear enough to calculate from
  rates, ask: "What's the total for this invoice?"
- Never mark an invoice as sent. Only the human does that.
- Payment terms always come from config.yaml.
- If this is the first invoice, start numbering at INV-001.
