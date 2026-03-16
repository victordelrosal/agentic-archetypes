# /new-lead

Capture a new lead and set up the first follow-up.

## Trigger

User says `/new-lead` or "I have a new lead"

## Flow

1. Ask for the essentials (only what's missing):
   - **Name**: Who is the lead?
   - **Company**: Where do they work? (optional)
   - **Source**: How did they find you? (referral, LinkedIn,
     cold outreach, event, etc.)
   - **Notes**: Any context (what they need, budget hints,
     timeline)

2. Create a client entry in .ops/state.json:
   ```
   {
     id: "client-[NNN]",
     type: "client",
     client: "[name]",
     contact_info: { email, phone, company, role } (capture
       whatever the user provides, leave rest null),
     status: "active",
     next_action: "send initial follow-up",
     due_date: [tomorrow],
     notes: "[source and context, e.g. 'met at a conference,
       needs brand work']",
     updated_at: [now]
   }
   ```

3. Delegate to **Client Manager** (agents/client-manager.md):
   - Draft a first-touch follow-up message
   - Save draft to workspace/follow-up-[client-name].md

4. Confirm to user:
   "[Name] added as a new lead. Follow-up draft is in
   workspace/ for your review. Due tomorrow."

## Rules

- Never skip the name. Everything else can be added later.
- If the user provides everything inline ("/new-lead Sarah
  from Acme, met at a conference, needs brand work"), don't
  ask redundant questions. Parse what's there.
- Set the follow-up due date to tomorrow by default.
- Never send the follow-up. Draft only.
