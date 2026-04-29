---
name: messaging-bridge
description: >
  Translate the message architecture into a go-to-market narrative. Connects
  purpose and positioning to the sales motion, product story, and pricing
  framing. Produces gtm-narrative.md with explicit handoff notes for
  sales-please, prd-please, and voice-please. Run after messaging-architect.
  Trigger when the user says things like "how does this connect to our sales
  process", "build the GTM narrative", or "we need to operationalize this."
system: messaging
integrations:
  required:
    - messaging/purpose-brief.md
    - messaging/positioning-statement.md
    - messaging/audience-map.md
    - messaging/message-architecture.md
  optional:
    - voice-please voice-profile.md
    - sales-please WORTH data
    - prd-please Strategic PRD
---

# Skill: messaging-bridge

**Purpose:** Translate the message architecture into an operational go-to-market narrative. Output is `messaging/gtm-narrative.md` with explicit handoff notes for the relevant siblings.

---

## Why This Skill Exists

Messaging that lives only in a document is not messaging -- it's an artifact. The gap between "we have a message architecture" and "our team actually uses it" is where most messaging investments die.

The bridge is the translation layer: how does the core claim become the opening line of an outbound sequence? How does the purpose anchor the way the product introduces itself at onboarding? How does the pricing page frame cost in terms of value, not in terms of what competitors charge?

messaging-bridge produces the structure that answers these questions -- and then explicitly hands off to the tools that own the execution: sales-please for the deal motion, prd-please for the product narrative, voice-please for content and copy.

---

## When to Use vs. Skip

**Use messaging-bridge when:**
- `audience-map.md` and `message-architecture.md` are complete and solid
- The team is ready to operationalize messaging into sales, product, or content
- The messaging exists but hasn't made its way into how the team actually works

**Skip messaging-bridge when:**
- The message architecture is incomplete (run messaging-architect first)
- Only the foundation exists (purpose-brief.md and positioning-statement.md) and the audience architecture hasn't been built

---

## Workflow

### Phase 1: Load Context

Before asking anything:

1. Read all existing messaging artifacts: purpose-brief.md, positioning-statement.md, audience-map.md, message-architecture.md.
2. Read voice-please artifacts if they exist.
3. Read sales-please data if it exists (WORTH qualification, ICP documentation).
4. Note what GTM motions are currently in play: inbound, outbound, PLG, partnerships, events, etc.

Ask: "What's the primary GTM motion right now? How is the team currently taking deals from first contact to close?"

---

### Phase 2: Sales Narrative

The sales narrative is the arc of the conversation the company has with a buyer from first contact to decision. It is not the same as the pitch deck -- it's the structure underneath it.

**Sales story arc:**
1. **The world as it is:** What is the buyer's current situation? What is the pain, the friction, the gap they're living with?
2. **Why it matters:** What is the cost of that situation continuing? (Financial, operational, reputational, opportunity)
3. **A different way:** What does the company believe is possible instead? (This is where purpose enters the sales conversation)
4. **The claim:** How specifically does the company deliver that different outcome? (This is the positioning claim, spoken to the buyer's context)
5. **Proof:** What evidence shows this is real and not just a pitch?
6. **The ask:** What is the specific next step the company is proposing?

Draft this arc using the message architecture. The core claim comes from positioning-statement.md. The proof points come from the primary buyer's entry in message-architecture.md.

*Why we build the arc: A sales team without a narrative arc improvises. Improvised sales conversations are inconsistent, harder to coach, and harder to learn from. The arc doesn't script every call -- it ensures every conversation has the same spine.*

---

### Phase 3: Product Narrative

The product narrative is how the product tells its own story -- in onboarding, in feature releases, in error states, in the help docs. It's not copy. It's the structure that makes copy coherent.

Ask: "Where does the product speak directly to users? Onboarding? Notifications? In-app prompts? Release notes?"

For each surface identified, draft a narrative direction note: what is the product trying to communicate at this moment, and how does it connect to the core claim?

*Why we include product narrative: A company whose sales pitch says one thing and whose product says another creates cognitive dissonance at exactly the moment the buyer becomes a user. The product is the last thing that needs to match the message -- and often the first place where messaging frameworks stop being applied.*

---

### Phase 4: Pricing Framing

Pricing pages and proposals fail when they communicate cost. They work when they communicate value.

Ask: "How is pricing currently framed in proposals or on the website? What does the buyer think they're paying for?"

Draft a pricing framing note: how should pricing be introduced in terms of the value it represents, not the features it includes? Which proof points from the message architecture most directly support the price?

*Why we address pricing: Pricing resistance is almost always a messaging problem. If the buyer says "that's too expensive," they mean "I can't see enough value to justify this cost." The solution is not a discount -- it's connecting the price to the value already established in the message architecture.*

---

### Phase 5: Sibling Handoff Notes

This is the operational core of messaging-bridge. For each relevant sibling, produce explicit handoff guidance.

**sales-please handoff:**

Name this explicitly: "The message architecture is ready to operationalize in your sales motion. The next step is taking this to sales-please."

Include:
- The per-audience core claims from message-architecture.md (formatted as inputs for outbound sequence authoring)
- The primary objections and responses (formatted as inputs for qualification scripts)
- The sales narrative arc from Phase 2
- Specific instruction: "Open sales-please and run the outbound sequence skill with the message architecture as your primary input."

*Why sales-please is the explicit next step: message architecture tells you what to say. Sales qualification tells you who the deal is for and whether it's worth pursuing. These are complementary -- a company with strong messaging and weak qualification will spend resources pitching the right story to the wrong deals. Name this plainly.*

**prd-please handoff:**

Include:
- The positioning statement (formatted as input for the PRD's positioning section)
- The product narrative notes from Phase 3
- The primary buyer and their core claim (formatted as input for the PRD's audience section)
- Specific instruction: "The gtm-narrative.md section 'Product Narrative' maps to the positioning and messaging sections of the Strategic PRD template."

**voice-please handoff:**

Include:
- The audience register notes from message-architecture.md (formatted as inputs for the register map)
- Any vocabulary rules or tone notes that surfaced during architecture work
- Specific instruction: "The register notes per audience in message-architecture.md should feed directly into voice-please's register map and audience language bank."

---

### Phase 6: Produce Artifact

Write the output artifact using the template at `templates/gtm-narrative.md`.

Present the draft to the user before saving. After confirmation, save to `messaging/gtm-narrative.md`.

After saving, surface the handoffs explicitly: "The message architecture is ready. Here's where to take it next: [list the relevant siblings and what each one does with this output]."

---

### Phase 7: Companion Doc and Playbook

Generate `messaging/gtm-narrative-companion.md` with:

- **Why structure:** Why the GTM narrative has the arc it has, and what each section is doing
- **Why voice:** What the framing choices in the sales narrative and product narrative are signaling
- **What to reuse:** The most reusable frames from this session (the pricing framing approach, the sales arc structure)
- **Do it yourself:** How to update the GTM narrative when the message architecture changes

Append an entry to `messaging/playbook.md`.

---

## Quality Standards

A good `gtm-narrative.md`:
- The sales narrative arc has a specific opening that describes the buyer's current situation accurately enough that the buyer nods
- Proof points are pulled from the message architecture and not invented here
- The product narrative section is specific enough to guide copy decisions, not just endorse them
- The pricing framing addresses the value-per-cost question, not just the cost
- Each handoff note names the specific artifact, the specific destination, and the specific instruction -- not just "hand this off to sales"
