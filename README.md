# Archetypes

**Ready-to-deploy AI organizations for individuals and micro-businesses.**

An archetype is a complete "organization in a box": an AI operations
team tailored to a specific business type. You install it, fill in
your details, and open Claude Code. Your business runs.

## Available Archetypes

| Archetype | For | Skills |
|-----------|-----|--------|
| [Freelancer](freelancer/) | Consultants, designers, developers, writers | /new-lead, /draft-proposal, /invoice, /weekly-review, /status |
| [Content Creator](content-creator/) | YouTubers, newsletter writers, educators, podcasters | /new-idea, /draft, /repurpose, /weekly-review, /status |
| [Remote Worker](remote-worker/) | Corporate employees, managers, analysts | /triage, /prep, /summarize, /weekly-review, /status |
| [E-commerce](ecommerce/) | Shopify owners, online retailers, DTC brands | /customer-reply, /new-product, /campaign, /weekly-review, /status |
| [Local Service](local-service/) | Gyms, salons, repair shops, coaches, agencies | /new-booking, /customer-reply, /promotion, /weekly-review, /status |

## How It Works

Every archetype shares the same chassis:

```
archetype-name/
  README.md          Human onboarding (2-min setup)
  CLAUDE.md          The brain (orchestrator)
  config.yaml        Your business details (personalization)
  agents/            Your AI team (4 specialists per archetype)
  skills/            Slash commands (5 per archetype)
  templates/         Domain-specific document templates
  .ops/              Operational state (auto-managed)
  workspace/         Where output lands for your review
```

**Same structure. Different business.** The chassis handles
orchestration, state management, session rituals, and escalation.
The domain layer (agents, skills, templates, config) is what
makes each archetype specific to your business type.

## Getting Started

### 1. Pick your archetype

Choose the one that matches your work. If you're a freelance
designer, pick Freelancer. If you run a Shopify store, pick
E-commerce.

### 2. Fill in config.yaml

Open the config file and enter your business details: name,
services, rates, tools, preferences. This is how the system
personalizes everything. Takes 60 seconds.

### 3. Open Claude Code

```bash
cd archetypes/freelancer   # or whichever you chose
claude
```

### 4. Say hello

The system detects this is your first run and walks you through
onboarding. It confirms your profile and asks about active work
to seed.

That's it. You're operational.

## What Makes This Different

**"Why not just use Claude Code directly?"**

You can. Claude Code is powerful. But it's a blank canvas.

Archetypes give you:

- **Structure**: Pre-designed workflows for your business type
- **Agents**: Specialized AI team members who know their role
- **Skills**: Push-button commands (/invoice, /new-lead) instead
  of figuring out what to ask
- **State**: Your business remembers what happened last session
- **Guardrails**: Nothing gets sent, committed, or fabricated
  without your approval

The difference between "a powerful AI tool" and
"an AI-powered organization" is structure.

## The Shared Chassis

Every archetype inherits these capabilities:

| Feature | What It Does |
|---------|--------------|
| **First Run** | Onboarding flow that personalizes the system |
| **Session Start** | Daily standup: what's pending, what's due |
| **Session End** | Daily close: update state, flag tomorrow |
| **Orchestrator** | Routes requests to the right agent or skill |
| **State Management** | Persistent business state across sessions |
| **Escalation Protocol** | Never decides for you on money, comms, or commitments |
| **No-Fabrication Rule** | Never invents data; asks when unsure |
| **Workspace** | All output lands in workspace/ for review |

## Requirements

- [Claude Code](https://claude.ai/claude-code) (Anthropic's CLI)
- A Claude subscription (Pro, Team, or Enterprise)
- 2 minutes to fill in config.yaml

## Who Made This

**Victor del Rosal** / [Agentive](https://agentive.ie)

Archetypes is a standalone product. For the enterprise/corporate
framework, see [Chairman](https://github.com/victordelrosal/chairman).

---

*Questions? Feedback? Want the paid installation?*
*Open an issue or contact [victor@agentive.ie](mailto:victor@agentive.ie)*
