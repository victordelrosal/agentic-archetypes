# Local Service Business Archetype

**Your service business, run by AI.**

You just installed the Local Service Business archetype. This
gives you a personal AI operations team: customer relations, a
scheduling coordinator, a marketing assistant, and an operations
manager, all coordinated by an orchestrator that acts as your
business COO.

## What You Have

```
local-service/
  CLAUDE.md        <- The brain (edit with caution)
  config.yaml      <- YOUR business profile (edit this first)
  agents/          <- Your AI team (4 specialists)
  skills/          <- Slash commands (/new-booking, etc.)
  templates/       <- Booking confirmations, promos, reviews
  .ops/            <- Your business state (auto-managed)
  workspace/       <- Where drafts and output land
```

## Getting Started (2 minutes)

### Step 1: Fill in your business profile

Open `config.yaml` and fill in your details: business name,
services (with durations and prices), hours, location, and
booking policies.

### Step 2: Open Claude Code in this directory

```bash
cd local-service
claude
```

### Step 3: Say hello

The system will detect this is your first run and walk you
through onboarding. It will confirm your business profile and
ask about upcoming bookings and open inquiries.

That's it. You're operational.

## What You Can Say

- "/new-booking Maria, personal training, Tuesday 10am"
- "/customer-reply" (then paste the inquiry or review)
- "/promotion fill slow Tuesday afternoon slots"
- "/status"
- "/weekly-review"
- "How should I respond to this Google review?"
- "What does my schedule look like this week?"

## How It Works

Every session:
1. The system checks today's bookings and open inquiries
2. You tell it what you want to work on
3. It delegates to the right agent(s)
4. Drafts land in `workspace/` for your review
5. When you wrap up, it updates state and flags tomorrow's
   schedule

No bookings confirmed without your approval. No replies sent
without your review.

## Need Help?

- Edit `config.yaml` to update your business profile
- Check `.ops/state.json` to see your business state
- Look in `.ops/log/` for session history
