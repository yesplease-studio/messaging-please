---
name: messaging-architect
description: >
  Map the stakeholder structure and build per-audience message architecture.
  Produces audience-map.md and message-architecture.md. Run after
  messaging-discover -- this skill requires an established purpose and
  positioning statement. Trigger when the user says things like "we're selling
  to different types of buyers", "help with audience messaging", or
  "build our message matrix."
system: messaging
integrations:
  required:
    - messaging/purpose-brief.md
    - messaging/positioning-statement.md
  optional:
    - voice-please voice-profile.md
    - voice-please register-map.md
    - sales-please ICP documentation
---

# Skill: messaging-architect

**Purpose:** Map the stakeholder structure and build per-audience message architecture. Output is `messaging/audience-map.md` and `messaging/message-architecture.md`.

---

## Why This Skill Exists

A company can have a solid positioning statement -- a real claim, anchored to a real buyer -- and still fail to close B2B deals consistently. The reason is almost always audience architecture: the core message is being delivered to the wrong person in the wrong form, at the wrong moment.

In a typical B2B deal, 6-10 people are involved in the buying decision (Gartner). The economic buyer cares about ROI and risk. The end user cares about whether the product makes their day better. The technical evaluator cares about whether it integrates cleanly. None of them need to hear the same message -- they need to hear the same *truth*, translated for what they actually care about.

This is not inconsistency. It is precision. A company that tells one story to everyone is either over-simplifying for the complex audience or over-explaining to the simple one. messaging-architect builds the architecture that makes precision possible.

---

## When to Use vs. Skip

**Use messaging-architect when:**
- `purpose-brief.md` and `positioning-statement.md` exist and are solid
- The company sells to multiple people in a deal (any B2B situation)
- The company is struggling to tailor messaging for different buyers without feeling inconsistent
- The sales team is ad-libbing different pitches and they're not connecting back to a common claim

**Skip messaging-architect when:**
- The foundation hasn't been built yet (run messaging-discover first)
- `audience-map.md` and `message-architecture.md` already exist and just need updating (run messaging-maintain)

---

## Workflow

### Phase 1: Load Context

Before asking anything:

1. Read `messaging/purpose-brief.md` and `messaging/positioning-statement.md`. Extract:
   - The core purpose claim
   - The primary ICP and what they care about
   - The positioning claim and differentiation
2. Read voice-please artifacts if they exist (voice-profile.md, register-map.md). Note register constraints and vocabulary rules.
3. Read sales-please ICP data if it exists. Note deal patterns and objection landscape.

Confirm with the user: "Based on purpose-brief.md, your primary buyer is [X]. Should we start there, or has the ICP shifted?"

---

### Phase 2: Stakeholder Mapping

Ask: "Walk me through a typical deal. Who shows up at each stage, and who has to say yes before it closes?"

Use the answer to identify which stakeholder roles are present. Standard roles (see SYSTEM.md):
- Economic buyer
- Champion
- End user
- Technical evaluator
- End consumer (B2B2C)

Add any company-specific roles (legal, compliance, procurement, executive sponsor).

*Why we ask: Before building per-audience messages, we need to know which audiences actually exist in the deal. A message matrix built for five roles when only three show up is wasted architecture. A matrix that ignores a blocker who shows up late is a gap that costs deals.*

**Shape-check:** If the user names more than five distinct roles, ask them to prioritize: "Which three of these, if they get the wrong message, most often kill deals?" Build depth there first.

---

### Phase 3: Audience Map

For each stakeholder role identified, establish:

1. **Name and context:** Role title, what they care about most in their job
2. **Relationship to the deal:** Do they initiate, evaluate, approve, block, or use?
3. **Primary concern about this purchase:** What question are they trying to answer? (Risk? ROI? Workflow? Integration? Political cover?)
4. **What they need to believe:** What is the one thing they have to believe for this deal to move forward from their side?
5. **Most likely objection:** What is the single most common thing that makes this role hesitate or block?

*Why we map before messaging: Without the map, per-audience messages are guesses. With the map, they are translations of a known truth into a known context. The map is what makes the architecture coherent.*

---

### Phase 4: Per-Audience Messaging

For each role in the audience map, build:

**Core claim (translated):**
The positioning statement, translated into the language and priorities of this specific person. Same truth, different emphasis. Not a different truth.

*Shape-check: If the translated claim has nothing in common with the positioning statement, something went wrong. Either the positioning is too generic to translate, or this role is being told something the rest of the company doesn't believe. Both are problems.*

**Proof points (2-3):**
Evidence that makes the claim credible for this role's specific priorities. A proof point that impresses the economic buyer may be invisible to the end user. Choose the evidence that answers the question this role is actually asking.

Proof point quality test: Is this verifiable? Is it specific? Does it answer a question this person would actually ask? If the answer to any of these is no, it's a brand promise, not a proof point.

**Primary objection and response:**
The most common resistance from this role, and a direct response. Not a reframe or a deflection -- an honest address of the concern.

**Register notes:**
How the message should sound for this person. (Formal/informal, data-heavy/story-driven, cautious/confident, etc.) These notes feed voice-please's register map and audience language bank.

*Why we ask: A message that's accurate but delivered in the wrong register doesn't land. The technical evaluator who gets the CEO pitch reads it as hype. The CFO who gets the product demo language doesn't see the business case. Register is part of the message.*

---

### Phase 5: Architecture Shape-Check

Review the complete message architecture before producing artifacts. Check:

- Does every audience's core claim trace back to the positioning statement?
- Are the proof points specific and verifiable, not generic brand promises?
- Are the register notes distinct enough to actually guide content creation?
- Is there a consistent thread running through all audience messages, even though the language differs?

If the architecture has an audience whose message doesn't connect back to the positioning, flag it: "This message for [role] is reading like a separate pitch, not a translation of the core claim. What is it about the core positioning that matters most to this person's situation?"

---

### Phase 6: Produce Artifacts

Write the output artifacts using the templates at `templates/audience-map.md` and `templates/message-architecture.md`.

Present both drafts to the user before saving. After confirmation, save to:
- `messaging/audience-map.md`
- `messaging/message-architecture.md`

After saving, offer to run `messaging-bridge` to translate the architecture into the GTM narrative.

---

### Phase 7: Companion Doc and Playbook

Generate `messaging/message-architecture-companion.md` with:

- **Why structure:** Why each audience gets its own entry, and what the consistent thread between them is doing
- **Why voice:** Why register notes belong in the message architecture, not just in the voice system
- **What to reuse:** The 2-3 most useful moves from this session (a proof point frame, an objection response, a useful distinction)
- **Do it yourself:** How to add a new audience to the architecture without running the full skill again

Append an entry to `messaging/playbook.md`.

---

## Quality Standards

A good `audience-map.md`:
- Names each stakeholder role clearly with a description that's specific to the company's deal dynamics
- Identifies what each role needs to believe (not just what they care about in general)
- Is honest about blockers -- the map isn't just the cheerleaders

A good `message-architecture.md`:
- Every audience's core claim traces visibly to the positioning statement
- Proof points are specific, not generic ("we reduced onboarding time from 14 days to 2 for teams like yours" not "fast onboarding")
- Register notes are distinct enough to actually guide someone writing content for that audience
- The architecture as a whole reads as one coherent company telling different versions of the same truth
