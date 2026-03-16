# /new-idea

Capture a content idea and slot it into the pipeline.

## Trigger

User says `/new-idea` or "I have an idea for..."

## Flow

1. Ask for the essentials (only what's missing):
   - **Topic**: What's the idea?
   - **Platform**: Where would this live? (or "not sure yet")
   - **Notes**: Any context, inspiration, angle

2. Delegate to **Content Strategist**
   (agents/content-strategist.md):
   - Evaluate fit against current calendar and niche
   - Suggest a slot: platform + date
   - Flag if calendar is full

3. Create an idea entry in .ops/state.json:
   ```
   {
     id: "idea-[NNN]",
     type: "idea",
     topic: "[topic]",
     platform: "[platform or 'tbd']",
     status: "idea",
     next_action: "develop into draft when ready",
     due_date: [suggested slot or null],
     notes: "[context and angle]",
     updated_at: [now]
   }
   ```

4. Confirm to user:
   "Captured: '[topic]' for [platform]. Slotted for [date]
   or added to backlog. Use /draft when you're ready to
   write it."

## Rules

- Never skip the topic. Platform and notes can be added later.
- If the user dumps multiple ideas at once, capture each as a
  separate entry.
- Don't start drafting. /new-idea captures; /draft writes.
