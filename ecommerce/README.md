# E-commerce Microbusiness Archetype

**Your online store, run by AI.**

You just installed the E-commerce Microbusiness archetype. This
gives you a personal AI operations team: customer service, a
product writer, a marketing assistant, and an operations analyst,
all coordinated by an orchestrator that acts as your store COO.

## What You Have

```
ecommerce/
  CLAUDE.md        <- The brain (edit with caution)
  config.yaml      <- YOUR store profile (edit this first)
  agents/          <- Your AI team (4 specialists)
  skills/          <- Slash commands (/customer-reply, etc.)
  templates/       <- Product listings, email campaigns
  .ops/            <- Your store state (auto-managed)
  workspace/       <- Where drafts and output land
```

## Getting Started (2 minutes)

### Step 1: Fill in your store profile

Open `config.yaml` and fill in your details: store name, platform,
products, brand voice, shipping policies, and marketing channels.

### Step 2: Open Claude Code in this directory

```bash
cd ecommerce
claude
```

### Step 3: Say hello

The system will detect this is your first run and walk you
through onboarding. It will confirm your store profile and ask
about open orders, customer issues, or campaigns.

That's it. You're operational.

## What You Can Say

- "/customer-reply" (then paste the customer message)
- "/new-product wireless earbuds, Bluetooth 5.3, 24hr battery"
- "/campaign summer clearance sale, 20% off all candles"
- "/status"
- "/weekly-review"
- "How should I respond to this 2-star review?"
- "Draft an email for our product launch next week"

## How It Works

Every session:
1. The system checks for open tickets, campaigns, and listings
2. You tell it what you want to work on
3. It delegates to the right agent(s)
4. Drafts land in `workspace/` for your review
5. When you wrap up, it updates state and flags urgent items

No customer replies sent without your approval. No discounts
authorized without your say-so.

## Need Help?

- Edit `config.yaml` to update your store profile
- Check `.ops/state.json` to see your store operations state
- Look in `.ops/log/` for session history
