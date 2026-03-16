# /summarize

Summarize a document, thread, or dataset.

## Trigger

User says `/summarize` or "summarize this" or "what does this say"

## Inputs

- **Content**: The material to summarize (pasted, described,
  or file path)
- **Purpose**: Why they need the summary (optional, helps
  focus the output)

## Flow

1. Delegate to **Research Analyst**
   (agents/research-analyst.md):
   - Produce a structured summary
   - Save to workspace/summary-[topic].md

2. If the summary reveals action items, create entries in
   .ops/state.json:
   ```
   {
     id: "task-[NNN]",
     type: "task",
     project: "[related project]",
     status: "active",
     next_action: "[action from the document]",
     due_date: [if mentioned, else null],
     notes: "surfaced from [document name]",
     updated_at: [now]
   }
   ```

3. Present the summary inline (don't just point to workspace).
   Keep it under 300 words. End with:
   "Full summary saved to workspace/. [N] action items
   captured."

## Rules

- If the content is too long to process at once, summarize
  in sections and combine.
- Always distinguish facts from interpretation.
- Never editorialize. Summarize what's there.
