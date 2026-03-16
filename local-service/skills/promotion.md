# /promotion

Plan and draft a local marketing promotion.

## Trigger

User says `/promotion` or "run a promotion" or "we need more
bookings"

## Inputs

- **Goal**: What the promotion should achieve (fill slow days,
  attract new customers, seasonal push)
- **Details**: Any specifics (discount, dates, services)

## Flow

1. Delegate to **Marketing Assistant**
   (agents/marketing-assistant.md):
   - Create promotion plan (goal, offer, audience, channels)
   - Draft copy for each channel (social, Google, email, flyer)
   - Save to workspace/promo-[name].md

2. Create a promotion entry in .ops/state.json:
   ```
   {
     id: "promo-[NNN]",
     type: "promotion",
     customer: null,
     service: "[target service or 'all']",
     status: "draft",
     next_action: "review promotion plan and approve",
     due_date: [proposed launch date],
     notes: "[goal and details]",
     updated_at: [now]
   }
   ```

3. Confirm to user:
   "Promotion plan for [goal] is in workspace/. Includes
   copy for [channels]. Review before launching."

## Rules

- Every discount amount must be confirmed by the human.
- Never authorize spending.
- Suggest timing based on booking patterns if available
  in state.
