# /draft

Research a topic and produce a content draft.

## Trigger

User says `/draft` or "write a..." or "draft a script for..."

## Inputs

- **Topic**: What to write about (can reference an existing
  idea from state by name)
- **Platform**: Where this will go (youtube, newsletter, etc.)
- **Brief**: Any direction or angle (optional)

## Flow

1. Check .ops/state.json for an existing idea matching the
   topic. If found, pull its notes and context.

2. Delegate to **Research Assistant**
   (agents/research-assistant.md):
   - Research the topic
   - Produce a brief in workspace/research-[topic].md
   - Goal: give the Writer data and angles to work with

3. Delegate to **Writer** (agents/writer.md):
   - Use the research brief as input
   - Use the topic brief from the user
   - Read config.yaml for voice, niche, platform conventions
   - Output to workspace/draft-[topic]-[platform].md

4. Update .ops/state.json:
   - If idea existed, update status to "drafting"
   - If new, create entry with type: "draft"
   ```
   {
     id: "content-[NNN]",
     type: "draft",
     topic: "[topic]",
     platform: "[platform]",
     status: "review",
     next_action: "review draft and approve or revise",
     due_date: [from calendar or 3 days from now],
     notes: "[any context]",
     updated_at: [now]
   }
   ```

5. Confirm to user:
   "Draft for '[topic]' ([platform]) is in workspace/.
   Review it and let me know if you want changes."

## Rules

- Always run Research Assistant before Writer.
- If platform isn't specified, check config.yaml for the
  creator's primary platform.
- Mark places that need the creator's personal voice with
  [YOUR TAKE: ...] rather than inventing opinions.
