---
name: messaging-discover
description: >
  Establish the messaging foundation: purpose, mission, vision, ICP, and
  positioning statement. This is the anchor for everything in the messaging
  chain. Run this first -- or when the foundation is unclear or needs rebuilding.
  Trigger when the user says things like "let's build our messaging", "help with
  positioning", "we don't have a clear story", or "what do we stand for."
system: messaging
integrations:
  required: []
  optional:
    - strategy-please workshop outputs
    - sales-please ICP / WORTH data
    - name-please naming-brief.md
---

# Skill: messaging-discover

**Purpose:** Establish the messaging foundation -- purpose, mission, vision, ICP, and positioning statement. Output is `messaging/purpose-brief.md` and `messaging/positioning-statement.md`.

---

## Why This Skill Exists

A company can have excellent copywriters, a well-funded brand team, and a professional sales deck -- and still have a messaging problem. The failure is almost never at the output layer. It is at the foundation: purpose that nobody can articulate, positioning that's actually a product description, an ICP that's defined by company size instead of buyer behavior.

messaging-discover builds the foundation. Everything produced in messaging-architect and messaging-bridge traces back to what gets established here. If this layer is soft, the chain breaks downstream and nobody can tell exactly why the messaging "doesn't land."

---

## When to Use vs. Skip

**Use messaging-discover when:**
- No messaging foundation exists
- The existing positioning statement is vague or feels like a product description
- The company has pivoted and the old foundation no longer applies
- Strategy or ICP work has been done elsewhere and needs to be synthesized into a messaging anchor

**Skip messaging-discover when:**
- `purpose-brief.md` and `positioning-statement.md` already exist and are solid
- The user wants to run messaging-architect with an existing foundation (confirm it's solid first, then proceed)

---

## Workflow

### Phase 1: Load Context

Before asking any questions:

1. Read `config/profile.md`. Note what's already known about the company, ICP, and existing messaging.
2. Check for sibling artifacts:
   - strategy-please workshop outputs (ICP definitions, positioning gaps)
   - sales-please WORTH data or ICP documentation
   - name-please naming-brief.md (category positioning, ICP register)
3. Note what's already answered in existing artifacts. Don't re-ask.

If no profile exists, run the SETUP.md onboarding first.

---

### Phase 2: Purpose Discovery

Ask these questions in sequence. Each includes a teach-through-choice rationale. In teach mode, surface the rationale. In standard mode, surface it if the user seems confused or resistant. In expert mode, ask the question without the rationale (but have it ready).

**Q1: Why did this company start?**

*Why we ask: Purpose isn't invented -- it's recovered. The reason the founder started the company almost always contains the real "why" that everything else should route back to. Product descriptions and feature lists come later; the origin comes first.*

Probe if the answer is product-focused ("we saw a gap in the market for X"). The gap is not the purpose. What was broken in the world that made the gap matter?

**Q2: What would be lost if this company disappeared?**

*Why we ask: This question surfaces the actual stake -- what the company is providing that isn't replaceable. If the answer is "nothing much, someone else would fill it," that's a signal the purpose needs work. If the answer is specific and stakes something, you have your anchor.*

**Q3: What does this company believe that most competitors in the category don't?**

*Why we ask: Differentiated positioning comes from differentiated belief. If the company believes the same things as its competitors, it will position the same way as its competitors. The belief is the seed of the claim.*

**Q4: Who ultimately benefits -- not the customer, but the person downstream?**

*Why we ask: In many companies (especially B2B SaaS), the buyer is not the person whose life changes. Understanding the downstream beneficiary often reveals a purpose the company hasn't articulated yet. It's also what makes purpose feel real rather than corporate.*

**Shape-check after Phase 2:** Review what emerged. If the purpose feels like a product description or a generic aspiration, name it: "That reads more like a value proposition than a purpose -- it tells me what you do, not why the world is better because you do it. Let's push one level deeper." Don't move to Phase 3 with a soft purpose.

---

### Phase 3: Mission and Vision

**Mission question:** "What does the company commit to doing, right now, in service of that purpose?"

Push if the answer is too aspirational ("we're working toward a world where..."). The mission is a present-tense operational commitment, not a vision. It should be accountable.

**Vision question:** "What does the world look like when this company has succeeded? Not the company -- the world."

Push if the answer is about company scale ("we'll be the market leader in..."). Vision is about impact, not market share.

**Distinguish clearly:** If the user conflates mission and vision, explain the distinction and why it matters: mission is accountability (you can hold the company to it today), vision is direction (it's the state you're building toward, not where you are).

---

### Phase 4: ICP Consolidation

If a clear ICP exists in sibling artifacts, read it and confirm with the user: "Strategy-please identified [X] as your primary buyer. Does that still hold, or has anything changed?"

If no ICP exists, ask:

**Q1: Who is the person who makes or approves the purchase decision?**
*Why we ask: The positioning statement is written for a specific buyer, not a company type or a demographic. The role, context, and priorities of that person determine whether the positioning claim lands.*

**Q2: What is the single biggest thing this person is trying to accomplish or avoid in their role?**
*Why we ask: Positioning that connects to a buyer's primary concern lands. Positioning that connects to a secondary concern gets noted but doesn't move people.*

**Q3: What are they using instead right now -- what's the current alternative?**
*Why we ask: Positioning is relative. You are not positioning in a vacuum; you are positioning against whatever the buyer considers an alternative. "No solution" is also a category.*

**Q4: What would have to be true for them to consider switching?**
*Why we ask: The trigger for consideration is usually the most honest window into what the buyer actually values.*

---

### Phase 5: Positioning Statement

Draft the positioning statement using the structure from SYSTEM.md:

```
For [target customer]
who [has this need / faces this situation],
[Company] is the [category]
that [delivers this outcome]
because [of this unique capability / approach].

Unlike [alternatives / status quo],
we [do this differently / better / in a way that matters to them].
```

**Shape-check after Phase 5:**

Review the draft against these tests:
- Does it name a specific buyer (not a company type)?
- Does it state a claim (not a feature)?
- Does the differentiation trace to a specific capability the company actually has?
- Could a competitor honestly say the same thing? If yes, the claim isn't differentiated.

If the draft fails any test, name the failure specifically. "This claim -- 'faster and more reliable' -- is what every competitor in your category says. What do *you* have that they don't, from the buyer's perspective?" Don't finalize a weak positioning statement.

---

### Phase 6: Produce Artifacts

Write the output artifacts using the templates at `templates/purpose-brief.md` and `templates/positioning-statement.md`.

Present both drafts to the user before saving. After confirmation, save to:
- `messaging/purpose-brief.md`
- `messaging/positioning-statement.md`

After saving, offer to run `messaging-architect` immediately.

---

### Phase 7: Companion Doc and Playbook

Generate `messaging/purpose-brief-companion.md` with:

- **Why structure:** Why the purpose/mission/vision are separated and what the distinction does
- **Why voice:** What made the specific language in the positioning statement land (or what to watch for)
- **What to reuse:** The 2-3 most useful moves from this session
- **Do it yourself:** How to run this play without the skill next time

Append an entry to `messaging/playbook.md` (create if it doesn't exist).

---

## Quality Standards

A good `purpose-brief.md`:
- Names a purpose that applies to the company and not to all competitors in the category
- Distinguishes clearly between purpose (why), mission (what now), and vision (what we're building toward)
- Is specific enough that a new team member would understand what decisions the company routes back to it

A good `positioning-statement.md`:
- Names a specific buyer
- Makes a claim that could be proven or disproven
- Differentiates against actual alternatives, not imaginary competitors
- Doesn't contain any banned phrases from SYSTEM.md
