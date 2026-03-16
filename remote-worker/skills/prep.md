# /prep

Prepare for a meeting: brief, agenda, talking points.

## Trigger

User says `/prep` or "prep for my meeting with..." or
"I have a meeting about..."

## Inputs

- **Who**: Who's in the meeting
- **What**: Topic or purpose
- **When**: Date and time (optional)

## Flow

1. Check .ops/state.json for related projects or prior
   interactions with attendees.

2. Delegate to **Meeting Prep** (agents/meeting-prep.md):
   - Create a meeting brief
   - Draft an agenda
   - Prepare talking points
   - Save to workspace/prep-[meeting-name].md

3. Create a meeting entry in .ops/state.json:
   ```
   {
     id: "meeting-[NNN]",
     type: "meeting",
     project: "[related project]",
     status: "active",
     next_action: "attend meeting, then capture action items",
     due_date: [meeting date],
     notes: "with [attendees] re: [topic]",
     updated_at: [now]
   }
   ```

4. Confirm to user:
   "Meeting prep for [topic] is in workspace/.
   [N] talking points ready. Anything you want to add?"

## Post-Meeting

If the user returns and says "meeting's done" or "debrief":
- Capture action items, decisions, and next steps
- Create task entries in .ops/state.json for each action item
- Update the meeting entry to status: "completed"

## Rules

- If the user gives minimal context ("prep for my 2pm"),
  ask what the meeting is about. Don't guess.
- Pull team and role context from config.yaml.
