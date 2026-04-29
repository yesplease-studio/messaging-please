# Setup

Before running any skill, messaging-please needs a company profile. The profile is required context -- messaging without it produces generic output that could belong to any company.

This takes about 10 minutes. You'll answer questions about the company, the buyers, and what messaging work has already been done. Claude will guide you through it.

---

## Step 1: Start the session

Open this repo in Claude Code and say **"let's set up messaging-please"** or **"I want to get started."**

Claude will check if `config/profile.md` already exists.

- **If it exists:** You're ready to run skills. Claude will read the profile and orient.
- **If it doesn't:** Continue below.

---

## Step 2: Answer the intake questions

Claude will ask about:

**The company**
- What does the company do, in plain language?
- Who is the primary buyer? (Role, context, what they care about most)
- What stage is the company at -- pre-product, early customers, scaling?

**The messaging situation**
- Does any existing messaging exist? (tagline, positioning statement, pitch)
- What's the core problem with the current messaging, if there is one?
- Has any strategy or sales work been done in the please family that should inform this?

**The stakeholders**
- In a typical deal, who is involved besides the primary buyer?
- Are there users who are different from the buyers?

**Sibling artifacts**
- Do strategy-please workshop outputs exist? (If yes, where?)
- Do sales-please ICP or WORTH data exist? (If yes, where?)
- Does a voice-please voice profile exist? (If yes, where?)

Claude will use these answers to create `config/profile.md`.

---

## Step 3: Review and confirm

Claude will present a draft `config/profile.md` before saving it. Review it and correct anything that's wrong or missing.

The profile is a living document -- you can update it as the company evolves. It's not a contract.

---

## Step 4: Choose where to start

Once the profile exists, Claude will route you to the right skill based on what's already been done:

- **No messaging foundation** → `messaging-discover` (purpose, ICP, positioning)
- **Foundation exists, no audience architecture** → `messaging-architect`
- **Architecture exists, not yet operationalized** → `messaging-bridge`
- **Existing messaging, needs updating** → `messaging-maintain`

---

## What gets created

Skills produce artifacts in a `messaging/` directory that lives in your workspace (not in this repo):

```
messaging/
├── purpose-brief.md
├── positioning-statement.md
├── audience-map.md
├── message-architecture.md
└── gtm-narrative.md
```

Not every engagement produces all five. Start with what's needed; the rest follows.
