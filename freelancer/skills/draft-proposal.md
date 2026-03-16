# /draft-proposal

Create a proposal by chaining research into writing.

## Trigger

User says `/draft-proposal` or "write a proposal for..."

## Inputs

- **Client name**: Who is this for? (must match a client in
  .ops/state.json, or create one)
- **Project brief**: What do they need? (can be a sentence
  or a paragraph)

## Flow

1. Check .ops/state.json for existing client context.
   If client doesn't exist, ask: "I don't have [name] in
   the system. Want me to add them as a new lead first?"

2. Delegate to **Research Analyst** (agents/research-analyst.md):
   - Research the client's company and industry
   - Produce a brief in workspace/brief-[client].md
   - Goal: give the Proposal Writer context to write
     something relevant, not generic

3. Delegate to **Proposal Writer** (agents/proposal-writer.md):
   - Use the research brief as input
   - Use the project brief from the user
   - Pull rates from config.yaml
   - Use templates/proposal-template.md for structure
   - Output to workspace/proposal-[client]-[project].md

4. Create a proposal entry in .ops/state.json:
   ```
   {
     id: "proposal-[NNN]",
     type: "proposal",
     client: "[name]",
     status: "draft",
     next_action: "review and send to client",
     due_date: [3 days from now],
     updated_at: [now]
   }
   ```

5. Confirm to user:
   "Proposal draft for [client] is in workspace/.
   Based on your [rate] rate, the quote is [amount].
   Review it and let me know if you want changes."

## Rules

- Always run Research Analyst before Proposal Writer.
  Research informs the proposal; skipping it produces
  generic output.
- Never invent rates. Pull from config.yaml. If the project
  doesn't fit standard rates, escalate.
- Default the review due date to 3 days from now.
- If the user provides a detailed brief, don't ask for
  more. Work with what you have.
