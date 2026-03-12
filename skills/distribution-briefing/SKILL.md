---
name: distribution-briefing
description: >
  Apply this skill when creating distribution assets from approved content,
  selecting social media formats, writing LinkedIn posts, planning distribution
  sequences, or briefing creative assets. Triggers when the user says "create
  distribution assets", "write a LinkedIn post for this", "which format should
  I use for this post", "build the campaign plan for this blog", "write the
  newsletter blurb", or when the distribution-agent needs format guidance.
version: 0.1.0
---

# Distribution Briefing — Axelerant Content Engine

Convert approved content into channel-optimized assets. This skill governs format selection, post construction, and distribution sequencing across all channels. It also briefs the Creative plugin on what visual assets to produce.

## The Non-Negotiable Gate

**Never create derivative assets before the main content is approved.** Distribution work begins only after the Narrative Writer's output has been reviewed and confirmed by a human. If you receive a draft, pause and ask for confirmation.

## Social Post Construction Framework

Every LinkedIn post has three jobs in sequence: stop the scroll, deliver value, earn the follow-through. Miss any one and the post fails.

### 1. Scroll-Stop Hook (First 2–3 Lines)

The first lines appear before "see more" — they are the entire ad. If they don't earn a click, nothing else matters.

Hook types that work:
- **Bold claim**: "We reduced a healthcare association's migration timeline by 40% — here's the architecture decision that made it possible."
- **Contrarian take**: "Most CMS migrations fail not because of technology — they fail because of the wrong migration sequence."
- **Specific outcome**: "Six months after launch, organic traffic was up 3x. It started with a structural decision most teams skip."
- **Provocative question**: "Why do enterprise Drupal migrations take 2x longer than planned, consistently, across every team?"

Hook anti-patterns to avoid:
- Generic openers: "In today's digital landscape...", "I'm excited to share...", "Proud to announce..."
- Starting with the company name: "Axelerant recently helped..."
- Starting with a feature list: "Our team used Drupal, AWS, and Acquia to..."
- Humble-bragging without specificity: "Incredible results from a recent project!"

### 2. Value-Adding Body

The body has one job: make the reader feel they got something real without needing to click the link.

What the body should deliver:
- The actual insight or lesson — not a teaser for the lesson
- Enough technical or strategic specificity that a practitioner recognizes it as real
- The "why behind the what" — decision rationale, not just outcome reporting
- 3–5 short paragraphs or structured line breaks, not bullets

What the body should NOT do:
- Gate-keep: "Read the full blog to find out how we did it"
- Be vague: "We used a creative approach to solve a complex challenge"
- Summarize generically: A post that describes nothing specific teaches nothing

### 3. Call to Action (Optional, Light Touch)

- For Tier 1 content: reference the full blog with a specific reason to read it ("the architecture section in the link goes deeper into X")
- For Tier 2: invite a conversation or reaction
- For Tier 3: CTA is optional — the post is the content

## Format Selection Matrix

The visual format amplifies the message type. See `references/social-post-understanding.md` for full format guidance.

| Content Type | Recommended Format | Why |
|--------------|-------------------|-----|
| Emotional story, team moment, client relationship | Short video (60–90 sec) | Video creates human connection; emotion needs face and voice |
| Process, methodology, step-by-step | Carousel (5–8 slides) | Swipeable steps; readers control the pace |
| Technical architecture, comparison, data | Infographic or single image | Dense data needs visual layout to parse |
| Thought leadership, perspective piece | Long-form text post | Complex arguments read better as narrative |
| Launch announcement, milestone | Single image + strong hook | Celebration moments are visual-first |
| Expert insight, opinion | Text-only | Strongest signal of genuine expertise — no visual needed |

## Distribution Assets by Tier

### Tier 1 Full Distribution Pack

Every Tier 1 blog gets all of the following:

**LinkedIn Post (Primary)** — 150–300 words. Scroll-stop hook + value body + blog reference. 3–5 hashtags (platform + industry + practice area).

**LinkedIn Post (Alternative Variant)** — Different angle or persona target. Same length. Identify what is different: hook type, audience, framing.

**Newsletter Blurb** — 80–120 words. Warmer, conversational tone. One sentence on why the reader should care. Clear link.

**Sales Enablement Summary** — 200–300 words. Written for BDR use in outreach. Positions the story as a proof point. Includes: "If your prospect is dealing with [X], share this piece."

**Campaign Snippet** — 40–60 words. For email campaign or LinkedIn sponsored content. Punchy, specific, designed to drive click-through.

**Internal Win Announcement** — 100–150 words. For Slack or internal comms. Celebrates the team. Tone: warm, proud, collegial.

**Platform POC Brief** (if platform-focused) — 150–200 words. For HubSpot / Drupal / Acquia / AWS partner contact. Positions as co-marketing material.

**Distribution Sequence Plan** — Week-by-week timing: publish → internal announcement → LinkedIn organic → newsletter → LinkedIn alternative → sponsored campaign → sales enablement → platform POC.

**Creative Brief** — Descriptions for: blog header image, LinkedIn visual (carousel or single), campaign ad visual. Written for the Creative plugin.

### Tier 2 Focused Activation Pack

- LinkedIn post (1 variant)
- Newsletter blurb
- Campaign snippet
- Simplified activation sequence

### Tier 3 Social Optimization

- Optimized LinkedIn post (primary)
- 2 alternative versions with different hooks
- Hashtag recommendations
- Format recommendation (text-only, image, carousel)

## Hashtag Strategy

Use 3–5 hashtags per post. Never repeat the same set across every post.

Categories:
- **Platform**: #HubSpot, #Drupal, #Acquia, #AWS, #Salesforce
- **Practice area**: #WebDevelopment, #DigitalEngineering, #UXDesign, #MarTech, #DigitalMarketing
- **Industry**: #HealthcareIT, #HigherEdTech, #AssociationManagement, #Ecommerce, #EnterpriseIT
- **Axelerant brand**: #Axelerant, #OpenSourceFirst, #DigitalTransformation

## Creative Briefing

When writing creative briefs for the Creative plugin, use this format:

```
CREATIVE BRIEF
Asset: [blog header / LinkedIn carousel / campaign ad / internal announcement]
Format: [image dimensions and type]
Concept: [visual idea in 2–3 sentences — what should be shown, what feeling it should evoke]
Key Text: [any text that must appear on the visual]
Style Notes: [tone, color palette direction, photography vs illustration preference]
Do Not: [any visual directions to avoid]
```

## Reference Files

- `references/social-post-understanding.md` — Full social post framework: scroll-stop theory, format logic, platform-specific best practices
- `references/channel-templates.md` — Copy templates for all 7 asset types
