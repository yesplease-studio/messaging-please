---
name: messaging-maintain
description: >
  Keep the message architecture current as the company evolves. Surfaces
  what has drifted, identifies which artifacts are affected, and proposes
  targeted updates. Run quarterly, after pivots, after new product launches,
  or after significant ICP shifts. Trigger when the user says things like
  "our messaging feels stale", "we've pivoted", "things have changed",
  or "let's update our positioning."
system: messaging
integrations:
  required:
    - messaging/purpose-brief.md
    - messaging/positioning-statement.md
  optional:
    - messaging/audience-map.md
    - messaging/message-architecture.md
    - messaging/gtm-narrative.md
    - voice-please voice-profile.md
    - sales-please recent WORTH data
---

# Skill: messaging-maintain

**Purpose:** Audit the existing message architecture against what has changed and produce targeted updates. Output is updated messaging artifacts and a maintenance log entry.

---

## Why This Skill Exists

Messaging architecture isn't a one-time deliverable. Markets move. Products change. Teams learn that the ICP they assumed doesn't match the customers who actually close. What was precise six months ago can drift into inaccuracy -- not all at once, but one unchecked assumption at a time.

The cost of stale messaging is invisible at first. Sales teams stop using it. Content gets written from gut instead of from architecture. Onboarding copy drifts from the core claim. By the time the disconnect is obvious, the team has been flying without a shared story for months.

messaging-maintain creates the discipline to check. It doesn't rewrite everything on every run -- it identifies what's drifted, proposes the minimal set of changes that restores coherence, and updates the artifacts that downstream work depends on.

---

## When to Use

- **Quarterly:** As a baseline cadence, regardless of whether something obviously changed
- **After a pivot:** New market, new ICP, new product focus
- **After a new product launch:** Adds a surface that may not have been in the original architecture
- **After a sustained messaging complaint:** "We have a messaging problem" often means the architecture is out of date
- **After significant new customer data:** If the customers closing are consistently different from the ICP in the architecture, the architecture needs updating

---

## Workflow

### Phase 1: Load Context

Read all existing messaging artifacts:
- purpose-brief.md
- positioning-statement.md
- audience-map.md (if it exists)
- message-architecture.md (if it exists)
- gtm-narrative.md (if it exists)

Note the `updated` date in each artifact's frontmatter. If no date is recorded, note that the age is unknown.

---

### Phase 2: What Has Changed

Ask the user to describe what has changed since the last messaging update. Prompt across four dimensions:

**Market:**
- Has the competitive landscape shifted? New entrants, repositioned competitors?
- Has the category changed how it's described or understood?
- Has the buyer's context changed -- new pressures, new priorities, new alternatives?

**Product:**
- New features, new products, or removed capabilities?
- Has the core value delivered to customers changed?
- Is there new proof (data, customer stories, outcomes) that wasn't available before?

**ICP:**
- Are the customers actually closing different from the ICP in the architecture?
- Has the company intentionally moved upmarket, downmarket, or into a new segment?
- Are there new stakeholder roles in deals that weren't accounted for?

**Team and execution:**
- Has the sales team stopped using parts of the architecture? Which parts, and why?
- Has content been drifting away from the architecture in practice?
- Has the product changed how it presents itself, independent of the messaging architecture?

*Why we ask across four dimensions: Messaging drift comes from four directions, and they produce different types of breakage. A change in the ICP breaks per-audience messaging. A change in the product breaks proof points. A competitive shift breaks positioning. A team execution drift is often a usability problem with the architecture itself.*

---

### Phase 3: Audit the Chain

Review the messaging chain against what has changed. Work from the top down:

**Purpose (purpose-brief.md):**
Does the company's stated purpose still apply? Has the product or market shifted in a way that makes the original purpose feel inaccurate or out of reach? (Purpose should be durable -- if it's drifting frequently, it wasn't deep enough to begin with.)

**Positioning (positioning-statement.md):**
Does the claim still differentiate against the current competitive landscape? Is the ICP still accurate? Does the "unlike alternatives" section still name the right alternatives?

**Audience architecture (audience-map.md, message-architecture.md):**
Are the stakeholder roles still accurate? Are any new roles missing? Are the core claims per audience still connecting to what those people actually care about? Are the proof points current?

**GTM narrative (gtm-narrative.md):**
Is the sales arc still accurate? Does the product narrative match how the product currently works? Is the pricing framing still defensible given changes to the product or market?

---

### Phase 4: Propose Changes

For each artifact that needs updating, propose a specific, minimal change. Show:
- What the current text says
- What it should say and why
- Which downstream artifacts are affected

Do not rewrite everything. Update what has drifted. Preserve what is still accurate.

If the audit reveals a break higher in the chain (purpose is wrong, positioning is outdated), flag that first. Updating the message architecture with a broken positioning is wasted work.

---

### Phase 5: Apply on Confirmation

Present the proposed changes. Wait for confirmation before writing.

After confirmation, apply the changes to the relevant artifacts. Update the `updated` date in each artifact's frontmatter.

Add a maintenance log entry to `messaging/tracking/maintenance-log.md` (create if it doesn't exist):

```
## YYYY-MM-DD

### What changed
[Summary of what was updated and why]

### Artifacts updated
- [artifact] -- [what changed]

### Downstream impact
- [Which siblings should be notified or re-run based on these changes]
```

---

### Phase 6: Downstream Notifications

After updating, identify which downstream systems are affected and name the next step:

- If positioning changed: sales-please outbound sequences may need updating. Voice-please conventions may need reviewing.
- If audience architecture changed: the message architecture inputs to sales-please and voice-please have changed.
- If GTM narrative changed: the prd-please product narrative section and voice-please content conventions may be affected.

Name these explicitly. The user should know what work the changes trigger downstream.

---

## Quality Standards

A good maintenance run:
- Updates what has drifted without rewriting what is still accurate
- Traces each proposed change to a specific reason (what changed, why this update follows)
- Produces a maintenance log entry that can be read by someone who wasn't in the session
- Identifies downstream impact so the user knows what to update next
