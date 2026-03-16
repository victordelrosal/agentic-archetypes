# /triage

Process inbox: prioritize messages, draft replies, flag urgent.

## Trigger

User says `/triage` or "process my inbox" or "what needs attention"

## Flow

1. Ask the user to paste or describe the messages to triage.
   (Claude Code cannot access email directly.)

2. Delegate to **Communications Manager**
   (agents/communications-manager.md):
   - Categorize each message: urgent, action needed, FYI, delegate
   - Draft replies for action-needed items
   - Save drafts to workspace/

3. Create entries in .ops/state.json for each actionable item:
   ```
   {
     id: "email-[NNN]",
     type: "email",
     project: "[related project or 'general']",
     status: "pending",
     next_action: "review draft reply and send",
     due_date: [today for urgent, this week for others],
     notes: "from [sender] re: [subject]",
     updated_at: [now]
   }
   ```

4. Present triage summary:
   "[N] urgent, [N] need replies, [N] FYI. Drafts for
   [N] replies are in workspace/. Review them?"

## Rules

- Never send anything. Draft only.
- Urgent items surface first in the summary.
- If a message relates to an existing project in state,
  link them.
