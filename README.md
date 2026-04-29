# messaging-please

An open-source, AI-native framework for building messaging architecture grounded in purpose, positioning, and audience context.

Takes purpose, ICP, stakeholder structure, and competitive context as raw material. Builds the full chain from why you exist to what you say to each person in a buying decision -- and produces artifacts that feed directly into your sales motion, product narrative, and voice system. Built to be used with [Claude Code](https://claude.ai/code).

Part of the [please family](https://github.com/yesplease-studio) of open-source frameworks from [Yes Please Studio](https://yesplease.studio).

---

## How it works

Most messaging problems look like a writing problem. They're not. The company has something to say -- it just has no architecture for who gets which version of it, why, and how it connects to everything else.

messaging-please is built on one principle: **messaging is a chain, not a menu.** Purpose anchors positioning. Positioning anchors your core claim. Your core claim gets translated -- not diluted -- for each audience in a deal. Break any link and everything downstream suffers.

Four phases:

1. **Discover.** Establish the foundation: purpose, mission, vision, ICP, and positioning statement. This is the anchor for everything that follows. Pulls from strategy-please or sales-please if those artifacts exist; builds from scratch if not.

2. **Architect.** Map the stakeholder structure and build per-audience messaging. Buyer, user, champion, blocker -- each person in a deal gets a tailored version of the core claim, grounded in the same purpose.

3. **Bridge.** Translate the message architecture into your go-to-market narrative. Connects purpose and positioning to sales motion, product story, and pricing. Explicit handoffs to sales-please, prd-please, and voice-please.

4. **Maintain.** Keep the architecture current as the company evolves. Surfaces what's drifted and proposes targeted updates.

## Who this is for

- **Founders and early teams** who have something real to say but no structure for saying it consistently
- **B2B companies** navigating deals where the buyer isn't the user and five people have to nod before anything moves
- **Companies at an inflection point** -- new market, new product, new ICP -- who need to rebuild their messaging from the foundation up
- **Consultants and advisors** who help companies with positioning and messaging and want a repeatable framework

## Quickstart

1. Open this repo in [Claude Code](https://claude.ai/code)
2. Claude will detect `CLAUDE.md.template` and load the system
3. Say **"let's build our messaging"** or **"help me get clear on our positioning"** and Claude will orient
4. If this is your first time, Claude will walk you through creating a company profile

Or go straight to a skill: **"run messaging-discover"**

## Skills

| Skill | What it does | When to use |
|-------|-------------|-------------|
| `messaging-discover` | Establishes purpose, mission, vision, ICP, and positioning statement | Starting from scratch, or when the foundation is unclear |
| `messaging-architect` | Maps audience structure and builds per-audience message architecture | After foundations are set, before sales or GTM work |
| `messaging-bridge` | Translates message architecture into GTM narrative; produces sibling handoff notes | When architecture is ready to operationalize |
| `messaging-maintain` | Updates messaging as company context changes | Quarterly, or after pivots, new products, or market shifts |

## Messaging artifacts

Skills produce structured artifacts that live in `messaging/`:

| Artifact | What it contains |
|----------|-----------------|
| `purpose-brief.md` | Purpose, mission, vision, Golden Circle anchors |
| `positioning-statement.md` | Core positioning: audience, category, claim, differentiator, proof |
| `audience-map.md` | Stakeholder roles, relationships, and decision dynamics |
| `message-architecture.md` | Per-audience messaging: core claim, proof points, objections, register notes |
| `gtm-narrative.md` | Sales narrative, product story, pricing framing, and handoff notes |

## Opinionated principles

- **Purpose first.** If you can't say why you exist beyond revenue, you don't have a positioning foundation -- you have a product description. The chain starts at purpose or it doesn't start.
- **Positioning is a claim, not a description.** Describing features is not positioning. A positioning statement stakes out a specific place in a specific buyer's mind.
- **Different messages for different audiences is not inconsistency.** It's precision. The buyer cares about ROI. The user cares about workflow. Both need to hear the truth; they need to hear different versions of it.
- **The chain has to hold.** Purpose anchors the claim. The claim translates per audience. The translation feeds the sales motion. If the chain breaks, the symptom shows up downstream -- usually in sales or as a "we have a messaging problem."
- **Messaging is a living document.** Markets move, ICPs evolve, products change. A messaging architecture that isn't maintained becomes a document nobody trusts.

## The please family

messaging-please is one of seven open-source frameworks from Yes Please Studio:

| Framework | What it does | Core question |
|-----------|-------------|---------------|
| [strategy-please](https://github.com/yesplease-studio/strategy-please) | Strategic workshop recommendation engine | "Where should we focus?" |
| [prd-please](https://github.com/yesplease-studio/prd-please) | Product requirements authoring and validation | "How do we build it reliably?" |
| [sales-please](https://github.com/yesplease-studio/sales-please) | Deal qualification and pipeline management | "Is this deal worth pursuing?" |
| [voice-please](https://github.com/yesplease-studio/voice-please) | Voice system definition and encoding | "What should we sound like?" |
| [design-please](https://github.com/yesplease-studio/design-please) | Design direction and encoding | "What should it look, feel, and act like?" |
| [name-please](https://github.com/yesplease-studio/name-please) | Name validation and generation | "Is this the right name?" |
| **messaging-please** | Messaging architecture and GTM narrative | "What do we say, and to whom?" |

messaging-please sits at the center of the family: it consumes outputs from strategy-please, sales-please, and name-please; and produces inputs for voice-please, prd-please, and sales-please.

## Directory structure

```
messaging-please/
├── CLAUDE.md.template     # How Claude operates in this system
├── SETUP.md               # Onboarding flow
├── README.md              # This file
├── config/
│   └── _template.md       # Company profile template
├── systems/
│   └── messaging/
│       └── SYSTEM.md      # Core methodology
├── skills/
│   ├── messaging-discover/  # Foundation: purpose, ICP, positioning
│   ├── messaging-architect/ # Audience mapping, message architecture
│   ├── messaging-bridge/    # GTM narrative, sibling handoffs
│   └── messaging-maintain/  # Ongoing updates
├── templates/             # Output artifact templates
│   ├── purpose-brief.md
│   ├── positioning-statement.md
│   ├── audience-map.md
│   ├── message-architecture.md
│   └── gtm-narrative.md
├── workflows/             # Composed skill sequences
│   ├── messaging-foundations.yaml  # discover → architect
│   └── messaging-gtm.yaml          # bridge
├── tracking/              # Effectiveness tracking
└── examples/              # Walkthroughs
```

## Self-serve vs. facilitated

Every skill in messaging-please produces useful output when run independently. You don't need a consultant to use this.

That said, positioning work (especially the claim and differentiation sections of `positioning-statement.md`) benefits significantly from having someone in the room who can push back on "that's a description, not a claim." The framework documents where facilitation adds the most value in `systems/messaging/SYSTEM.md`.

## License

MIT
