# Freelancer Archetype

**Your freelance business, run by AI.**

You just installed the Freelancer archetype. This gives you a
personal AI operations team: a client manager, a proposal writer,
a research analyst, and an admin assistant, all coordinated by
an orchestrator that acts as your COO.

## What You Have

```
freelancer/
  CLAUDE.md        <- The brain (edit with caution)
  config.yaml      <- YOUR business details (edit this first)
  agents/          <- Your AI team (4 specialists)
  skills/          <- Slash commands (/new-lead, /invoice, etc.)
  templates/       <- Proposals, invoices, emails
  .ops/            <- Your business state (auto-managed)
  workspace/       <- Where drafts and output land
```

## Getting Started (2 minutes)

### Step 1: Fill in your config

Open `config.yaml` and fill in your details: name, services,
rates, timezone, and tools you use. This is how the system
personalizes everything.

### Step 2: Open Claude Code in this directory

```bash
cd freelancer
claude
```

### Step 3: Say hello

The system will detect this is your first run and walk you
through onboarding. It will confirm your business profile
and ask if you have active clients or projects to seed.

That's it. You're operational.

## What You Can Say

Here are some things to try:

- "I have a new lead named Sarah from Acme Corp"
- "Write a proposal for a 3-month UX redesign"
- "Research the fintech market in Ireland"
- "Draft a follow-up email to Carlos"
- "Invoice Acme for the brand project"
- "What's pending this week?"
- "Prepare me for my meeting with Sarah tomorrow"

The orchestrator figures out which agent handles it. You just
talk naturally.

## How It Works

Every session:
1. The system checks your business state and tells you what's
   pending
2. You tell it what you want to work on
3. It delegates to the right agent(s)
4. Drafts land in `workspace/` for your review
5. When you wrap up, it updates state and flags tomorrow's
   priorities

Nothing goes out without your approval. Nothing gets fabricated.
If it doesn't know something, it asks.

## What's in workspace/?

All drafts, research briefs, and documents your agents produce.
Nothing here is final until you approve it. Think of it as your
team's shared desk.

## Need Help?

- Edit `config.yaml` to update your business details
- Check `.ops/state.json` to see your current business state
- Look in `.ops/log/` for session history
- Check `.ops/escalations/` for decisions waiting on you
