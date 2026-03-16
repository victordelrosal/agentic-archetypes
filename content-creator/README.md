# Content Creator Archetype

**Your content business, run by AI.**

You just installed the Content Creator archetype. This gives you
a personal AI content team: a strategist, a writer, a researcher,
and a distribution manager, all coordinated by an orchestrator
that acts as your content COO.

## What You Have

```
content-creator/
  CLAUDE.md        <- The brain (edit with caution)
  config.yaml      <- YOUR creator profile (edit this first)
  agents/          <- Your AI team (4 specialists)
  skills/          <- Slash commands (/new-idea, /draft, etc.)
  templates/       <- YouTube scripts, newsletters, social posts
  .ops/            <- Your pipeline state (auto-managed)
  workspace/       <- Where drafts and output land
```

## Getting Started (2 minutes)

### Step 1: Fill in your profile

Open `config.yaml` and fill in your details: name, niche,
platforms, posting schedule, voice, and tools. This is how the
system personalizes everything.

### Step 2: Open Claude Code in this directory

```bash
cd content-creator
claude
```

### Step 3: Say hello

The system will detect this is your first run and walk you
through onboarding. It will confirm your creator profile and
ask if you have content in progress.

That's it. You're operational.

## What You Can Say

Here are some things to try:

- "/new-idea I want to do a video about AI replacing managers"
- "/draft a newsletter about productivity myths"
- "/repurpose my latest YouTube script for LinkedIn"
- "/status"
- "/weekly-review"
- "What's trending in AI right now?"
- "Write show notes for my podcast episode on remote work"

The orchestrator figures out which agent handles it. You just
talk naturally.

## How It Works

Every session:
1. The system checks your content pipeline and tells you
   what's pending
2. You tell it what you want to work on
3. It delegates to the right agent(s)
4. Drafts land in `workspace/` for your review
5. When you wrap up, it updates state and flags upcoming
   deadlines

Nothing gets published without your approval. Your voice is
the product; the AI handles the operations around it.

## What's in workspace/?

All drafts, scripts, research briefs, and social posts your
agents produce. Nothing here is final until you approve it.
Think of it as your team's shared desk.

## Need Help?

- Edit `config.yaml` to update your creator profile
- Check `.ops/state.json` to see your content pipeline
- Look in `.ops/log/` for session history
- Check `.ops/escalations/` for decisions waiting on you
