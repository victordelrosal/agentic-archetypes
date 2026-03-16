# Remote Knowledge Worker Archetype

**Your corporate workload, managed by AI.**

You just installed the Remote Knowledge Worker archetype. This
gives you a personal AI operations team: a communications manager,
a meeting prep specialist, a research analyst, and a documentation
writer, all coordinated by an orchestrator that acts as your
work COO.

## What You Have

```
remote-worker/
  CLAUDE.md        <- The brain (edit with caution)
  config.yaml      <- YOUR work profile (edit this first)
  agents/          <- Your AI team (4 specialists)
  skills/          <- Slash commands (/triage, /prep, etc.)
  templates/       <- Meeting briefs, decision docs, status updates
  .ops/            <- Your work state (auto-managed)
  workspace/       <- Where drafts and output land
```

## Getting Started (2 minutes)

### Step 1: Fill in your profile

Open `config.yaml` and fill in your details: name, role, company,
team, tools, and recurring meetings.

### Step 2: Open Claude Code in this directory

```bash
cd remote-worker
claude
```

### Step 3: Say hello

The system will detect this is your first run and walk you
through onboarding. It will confirm your work profile and ask
about active projects and deadlines.

That's it. You're operational.

## What You Can Say

- "/triage" (then paste your emails)
- "/prep for my meeting with the product team tomorrow"
- "/summarize this quarterly report"
- "/status"
- "/weekly-review"
- "Draft a memo on the Q2 roadmap changes"
- "Write a decision doc: should we build or buy?"

## How It Works

Every session:
1. The system checks your tasks and tells you what's pending
2. You tell it what you want to work on
3. It delegates to the right agent(s)
4. Drafts land in `workspace/` for your review
5. When you wrap up, it updates state and flags tomorrow's
   priorities

Nothing gets sent without your approval. No commitments made
on your behalf.

## Need Help?

- Edit `config.yaml` to update your work profile
- Check `.ops/state.json` to see your current task state
- Look in `.ops/log/` for session history
