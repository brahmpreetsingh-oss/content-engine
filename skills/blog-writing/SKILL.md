---
name: blog-writing
description: >
  This skill should be used when writing any long-form blog content for
  Axelerant, including use-case driven blogs, platform-focused blogs, and
  industry thought leadership pieces. Triggers whenever someone asks to
  "write a blog", "draft the article", "create the Tier 1 content", or
  when the narrative-writer agent needs format and style guidance.
version: 0.1.0
---

# Blog Writing — Axelerant Content Engine

Write every blog as if it will be read by a senior digital decision-maker who has seen hundreds of generic agency blogs and is ready to stop reading the moment they detect padding, vagueness, or self-promotion.

## Non-Negotiable Format Rules

- **Length by type**:
  - Standard blog post: **600–900 words** — the default. Tight, purposeful, no padding.
  - Long-form deep-dive: **1,100–1,400 words** — only when technical depth genuinely demands it (multi-stage architecture, complex migration). Must be explicitly classified as such.
  - Never write to fill length. A 700-word post that lands every point is better than a 1,400-word post that repeats itself.
- **Structure**: Flowing prose — not bullet dumps. If a list is unavoidable, introduce it and follow it. No more than one list per post.
- **No generic openings**: Never start with "In today's digital landscape...", "As technology evolves...", or "In an era of digital transformation..."
- **No client names**: Always use anonymized descriptors ("a global healthcare association", "a mid-market SaaS company")
- **No fabrication**: If a detail is not in the approved dossier, flag it as missing — do not invent it
- **Always include**: Headline options (3), subheadline, meta description (150 chars), excerpt (2-3 sentences), CTA options (2)

## Raw and Authentic: The Tone Mandate

This is the most commonly violated rule. Fix it before anything else.

**Polished content loses engineers.** A blog that reads like it went through three rounds of marketing feels fake. The reader closes the tab. The goal is to sound like a practitioner wrote it after solving a hard problem — not like an agency wrote it to win a client.

What raw and authentic means in practice: write the way the team actually talks about the problem. If the honest answer is "it was messier than we expected," say that. Short sentences. Direct language. No hedging with phrases like "it is important to note that" or "it is worth highlighting." First-person plural is fine — "We ran into...", "We tried X first, it didn't work, here's why." Tradeoffs, reversals, and things that were harder than expected build trust; polished outcome statements do not. A post should feel like it was written by someone who lived it, not by someone who read about it.

**Reject any draft that sounds like it was written to impress. Write like you're telling someone what actually happened.**

## Image and Screenshot Directive

Raw, genuine visuals are first-class content. They are not decorative — they are evidence.

When source screenshots or visual artifacts are available from the engagement — Slack threads, Granola meeting notes, tool outputs, dashboards, terminal outputs, before/after comparisons, whiteboard photos from calls — they must be mapped to the relevant use case in the post. Do not save images for the end. Place each visual at the exact moment in the narrative where it proves the point being made.

**Raw is better than polished.** A screenshot of an actual Slack message showing a client's reaction, an unedited terminal output, a rough whiteboard from a planning session — these signal authenticity more than a cleaned-up diagram ever will.

Caption every image with context, not a description. Not "Screenshot of the dashboard." Instead: "Weekly content output before and after the pipeline went live — the team went from 2 posts/month to 11." When pulling visuals from different sources (HubSpot, Granola, Slack, Google Drive), label the source in the caption so the reader knows where the evidence comes from.

**Image sourcing priority — follow this order for every image placement:**

1. **Real artifact from the engagement** — screenshot from Slack, Granola, HubSpot, Google Drive, terminal output, dashboard, whiteboard photo. Always preferred. Always more credible.
2. **Generated technical illustration** — if no real artifact exists for a placement, generate a clean technical image that accurately represents the concept: architecture diagrams, flow diagrams, before/after state comparisons, data flow maps, decision trees, system component maps. These must be technically accurate to the engagement — not generic stock-style illustrations. They should look like something an engineer drew to explain a real system, not a stock infographic.
3. **[IMAGE NEEDED] placeholder** — only use this as a last resort when the concept requires a real screenshot that cannot be generated (e.g., an actual client Slack reaction, a real metric from a live dashboard). Flag it clearly: `[IMAGE NEEDED: brief description — source: Slack / Granola / tool output]` so the human reviewer can supply it before publish.

Never leave a post with a visual gap and no compensation. If a slot cannot be filled with a real artifact and cannot be accurately generated, the prose must do the visual work — specific numbers, named tools, concrete sequences of events. But generated technical images are almost always a better fallback than a placeholder or prose alone.

## Solving, Not Selling: The Content Principle

Every Axelerant blog is written as a resource, not a pitch. The reader should finish the piece feeling more informed and capable — not sold to.

**What this means in practice:**
- Lead with the reader's problem, not Axelerant's solution. The opening establishes a challenge the reader recognises, not a capability Axelerant wants to claim.
- Axelerant's involvement is introduced as evidence, not as the point. We worked on this; here is what we learned; here is what you can take from it.
- The problem is explored with full honesty — what made it hard, what failed, what tradeoffs existed. Credibility is earned by showing difficulty, not hiding it.
- CTAs are invitations, not closes. "If you're navigating this, we'd be glad to think through it with you" not "Contact us to get started."
- The reader should be able to apply something from the piece even if they never work with Axelerant. That utility is what builds trust.

Reject any draft that reads like a case study designed to impress. Write content that is designed to be useful.

---

## The Three Blog Types

### Use-Case Driven
**Target persona: CTO, Engineering Director, Principal Architect, Technical Lead**
Core question the blog must answer: "How did they actually do this, and what can I learn?"

**Technical depth is non-negotiable for this type.** These pieces are written for engineers and technical leaders who will stop reading the moment content is too surface-level, too vague, or sounds like it was written by marketing. Do not flatten complexity for a general audience.

Approach:
- Lead with the engineering or delivery problem in precise technical terms
- Show the thinking behind the approach — alternatives seriously considered, constraints honored, decisions made under real conditions
- Be specific about implementation: what was built, how it was structured, what tradeoffs were made and why
- Assume fluency — do not explain basics, do not use metaphors where technical language is available
- Name the tools, patterns, architectural decisions, and failure modes — vague claims like "we optimized the platform" or "we improved performance" are unacceptable
- Include something the technical reader hasn't thought about or hasn't seen framed this way before
- End with a concrete, transferable takeaway — a pattern, a decision framework, a warning, something useful

**What a reader should think at the end:** "This team genuinely knows what they're doing. I learned something."

### Use-Case with Platform Focus
**Target persona: CTO, CDO, Technology Evaluator, Engineering Director assessing a specific platform**
Core question the blog must answer: "Would this platform be right for us, and did it actually do what was needed?"

**Technical depth is non-negotiable for this type.** The reader is in evaluation mode — they understand the platform in question or are learning it seriously. Generic claims about platform capability are worse than useless; they signal the author doesn't know the platform well.

Approach:
- Same engineering depth as use-case driven, plus explicit platform decision context
- Explain why this platform was chosen — including the alternatives that were rejected and why. "We evaluated X, Y, and Z; here is why the client went with this platform and what that unlocked" is infinitely more useful than "they chose Drupal."
- Include platform-specific technical detail sufficient for an evaluation context: architecture decisions, integration patterns, performance at scale, known limitations
- Be honest about platform limitations or implementation complexity — credibility comes from candor, not cheerleading
- Do not make the piece promotional for the platform. Make it decision-useful. The reader should be able to make a more informed choice after reading it.
- If Axelerant has specific experience with this platform's ecosystem (Acquia, AWS, HubSpot), show the depth of that — not as a credential claim, but as the source of the practical detail

**What a reader should think at the end:** "This is the most useful thing I've read about this platform in the context of a real project."

### Industry
**Target persona: Chief Digital Officer, VP Digital, Executive stakeholder in a specific sector**
Core question the blog must answer: "What does this mean for my organization and my industry?"

**Industry blogs must cover three elements — all three, every time:**

1. **The impact Axelerant's engagement is creating**: Not a generic outcome claim. The specific, concrete result in that industry context — what changed, for whom, and why it matters in the sector's terms (not just in platform terms). Quantify where possible. Contextualize always.

2. **The north star of that industry**: What does "winning" look like for organizations in this sector? What are the structural pressures, compliance constraints, buyer behaviors, budget cycles, or competitive dynamics that shape what they're trying to achieve? The reader should feel the blog was written by someone who genuinely understands their world — not by someone who ran a project in their industry once.

3. **Orchestrated thinking**: Show how different elements work together toward the same outcome — how the platform choice connected to the delivery approach, how the UX decisions connected to the marketing strategy, how the technical architecture enabled the business goal. Industry readers manage complexity across functions; content that shows cross-functional thinking lands harder than content that shows technical depth alone.

Additional approach:
- Include at minimum 2–3 external references (analyst research, industry reports, public data) to establish the broader pattern
- Clearly separate engagement-derived insight from external trend commentary — the reader should know which is which
- Write as a practitioner who has operated inside this industry's problems, not as a vendor who happened to work for an industry client
- End with implications, not summaries. "Here is what this means for organizations like yours" — not "in conclusion, digital transformation is important."

## Engagement Theme Framing

Adjust depth and focus based on the classified theme:

**Strategy**: High-level planning, frameworks, long-term vision. Tone: confident, directional.
**Design**: UX rationale, creative decisions, design thinking process. Tone: thoughtful, human-centered.
**Build**: Technical specificity, implementation logic, engineering decisions. Tone: precise, credible.
**Grow**: Optimization, metrics, iteration, scaling lessons. Tone: analytical, evidence-based.
**Delivery**: Project outcome, team structure, risk management, client relationship. Tone: authoritative, reassuring.
**Account Management**: Relationship depth, trust-building, expansion signals. Tone: warm, strategic.

## Blog Structure Template

Two formats depending on length classification:

### Standard Blog (600–900 words) — default

Section 1 — **Hook**: One sharp problem statement or tension. 1 paragraph. No preamble.
`[IMAGE if available: visual that frames the problem — screenshot, before state, real artifact]`

Section 2 — **What we ran into**: The specific constraint or difficulty. What made this hard. 2 paragraphs max. Be honest about the messy parts.
`[IMAGE if available: screenshot showing the problem state, error, or friction point]`

Section 3 — **What we did and why**: The decision + the reasoning. Not exhaustive — just enough to show real thinking. 2 paragraphs.
`[IMAGE if available: approach diagram, Slack exchange showing the decision, tool output mid-process]`

Section 4 — **What changed**: The outcome, stated plainly. Numbers where you have them. 1 paragraph.
`[IMAGE if available: after state, result screenshot, dashboard showing the change]`

Section 5 — **What you can take from this**: One concrete, transferable point. 1 paragraph + CTA.

### Long-Form Deep-Dive (1,100–1,400 words) — for complex technical content only

Extends the standard structure with:
- Section 2 expanded to cover full challenge depth (3 paragraphs)
- Section 3 split into Approach and Execution (3 paragraphs each)
- Section 4 expanded with quantified outcomes and broader implications (2–3 paragraphs)
- Images mapped throughout — minimum 3 placements for a piece of this length

## Reference Blog Analysis

Analyze the following Axelerant reference blogs for structure and flow (not content). Use them as the benchmark for what a well-crafted Axelerant blog reads like:

See `references/reference-blogs.md` for the URLs and flow analysis notes.

## Case Study References

Where relevant, link to related success stories from https://www.axelerant.com/success-stories to support claims and demonstrate track record.
