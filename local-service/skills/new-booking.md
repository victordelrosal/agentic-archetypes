# /new-booking

Capture a booking request, check availability, confirm.

## Trigger

User says `/new-booking` or "someone wants to schedule..." or
"new appointment"

## Inputs

- **Customer**: Who's booking
- **Service**: What service they want
- **When**: Preferred date and time

## Flow

1. Ask for essentials (only what's missing):
   - Customer name
   - Service type
   - Preferred date/time

2. Delegate to **Scheduling Coordinator**
   (agents/scheduling-coordinator.md):
   - Check availability in .ops/state.json
   - Check business hours from config.yaml
   - If conflict, suggest 2-3 alternatives

3. Create a booking entry in .ops/state.json:
   ```
   {
     id: "booking-[NNN]",
     type: "booking",
     customer: "[name]",
     service: "[service]",
     status: "pending",
     next_action: "confirm with customer",
     due_date: "[booking date/time]",
     notes: "[preferences, e.g. 'prefers mornings']",
     updated_at: [now]
   }
   ```

4. Draft a confirmation message in workspace/.

5. Confirm to user:
   "[Customer] booked for [service] on [date] at [time].
   Status: pending your confirmation. Draft confirmation
   in workspace/."

## Rules

- Never confirm a booking without human approval (status
  starts as "pending", not "confirmed").
- If requested time is outside business hours, escalate.
- If the user provides everything inline, don't ask
  redundant questions.
