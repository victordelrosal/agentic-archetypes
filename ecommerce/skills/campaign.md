# /campaign

Plan and draft a marketing campaign or promotion.

## Trigger

User says `/campaign` or "run a promotion" or "email campaign for..."

## Inputs

- **Goal**: What this should achieve (clear inventory, launch
  product, seasonal sale, re-engage customers)
- **Details**: Any specifics (discount amount, products, dates)

## Flow

1. Delegate to **Marketing Assistant**
   (agents/marketing-assistant.md):
   - Create campaign plan (goal, offer, audience, channels,
     timeline)
   - Draft copy for each channel
   - Save to workspace/campaign-[name].md

2. If relevant, delegate to **Operations Analyst**
   (agents/operations-analyst.md):
   - Pull product or inventory context to inform the campaign

3. Create a campaign entry in .ops/state.json:
   ```
   {
     id: "campaign-[NNN]",
     type: "campaign",
     customer: null,
     product: "[product or 'store-wide']",
     status: "draft",
     next_action: "review campaign plan and approve",
     due_date: [proposed launch date],
     notes: "[goal and details]",
     updated_at: [now]
   }
   ```

4. Confirm to user:
   "Campaign plan for [goal] is in workspace/. Includes
   copy for [channels]. Review before launching."

## Rules

- Every discount amount must be confirmed by the human.
- Never authorize spending.
- Check .ops/state.json for conflicting active campaigns.
