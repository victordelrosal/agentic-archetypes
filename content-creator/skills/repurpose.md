# /repurpose

Turn one piece of content into formats for other platforms.

## Trigger

User says `/repurpose` or "turn this into..." or "post this
on [platform]"

## Inputs

- **Source**: Which piece to repurpose (title, topic, or file
  in workspace/)
- **Targets**: Which platforms (optional; defaults to all
  platforms in config.yaml)

## Flow

1. Locate the source content:
   - Check workspace/ for the file
   - Check .ops/state.json for the entry
   - If not found: "I can't find '[source]'. Is it in
     workspace/ or do you want to paste it?"

2. Verify the source is approved/published. If still in draft:
   "This piece is still in draft status. Repurpose anyway,
   or finalize first?"

3. Delegate to **Distribution Manager**
   (agents/distribution-manager.md):
   - Read the source content
   - Produce platform-native versions for each target
   - Save to workspace/ (e.g. workspace/linkedin-[topic].md)

4. Create distribution entries in .ops/state.json for each
   platform version:
   ```
   {
     id: "dist-[NNN]",
     type: "task",
     topic: "[topic] ([platform] version)",
     platform: "[target platform]",
     status: "review",
     next_action: "review and publish",
     due_date: [next posting slot per config schedule],
     notes: "repurposed from [source id]",
     updated_at: [now]
   }
   ```

5. Confirm to user:
   "Created [N] versions: [list platforms]. All in workspace/
   for review. None posted yet."

## Rules

- Never post or publish. Prepare only.
- Always check if the source was already repurposed for a
  target platform (avoid duplicates).
- Each platform version must be native, not copy-pasted.
