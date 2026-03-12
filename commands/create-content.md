---
description: Guided content creation from an engagement story
allowed-tools: Task, Read, Write, WebFetch
argument-hint: [optional: paste story brief or type "new" to start fresh]
---

Run the guided content creation workflow for Axelerant engagement storytelling.

This is the primary command for turning an engagement story into publishable content. It follows a structured, gated flow — do not skip any gate or proceed without user confirmation at each stage.

## FLOW OVERVIEW

detect input → ask 7 primary questions → classify into tier → confirm tier → suggest topics (if Tier 1) → confirm topic → ask depth questions → confirm outline → create content

---

## STEP 1: CHECK FOR INPUT

If $ARGUMENTS contains a story brief or reference: use it to pre-fill answers to the questions below where possible, and ask only for missing information.

If $ARGUMENTS is empty or "new": start from the beginning with the 7 primary questions.

---

## STEP 2: ASK THE 7 PRIMARY QUESTIONS

Ask all questions in a single message. Do not proceed until all 7 are answered.

Present each question with brief option descriptions:

**Q1 — Service Scope**
What is the service scope for this engagement?
a) Digital Engineering — technical builds, migrations, platforms, integrations
b) Experience Design — UX, design systems, user research, interface design
c) Digital Marketing — campaign strategy, SEO, analytics, marketing operations

**Q2 — Engagement Theme**
What is the theme of this engagement?
a) Strategy — planning, frameworks, long-term vision
b) Design — UX, design decisions, creative process
c) Build — implementation, development, engineering
d) Grow — optimization, scaling, performance improvements
e) Delivery — project delivery, team, risk, client outcomes

**Q3 — Target Audience**
Who is this content targeting?
a) The Executive — CEO, CMO, CDO, VP Digital (business outcomes, ROI, risk)
b) The Technical Stakeholder — CTO, Architect, Engineering Director (implementation depth)
c) The Delivery Stakeholder — PM, Program Manager, Delivery Lead (process, team, risk)
d) The Marketing Stakeholder — Marketing Director, Demand Gen (pipeline, channels)

**Q4 — Who Benefits**
Who will benefit from this content/solution? (Free text — describe the reader who gains the most)

**Q5 — Engagement Story**
What is the engagement story? Elaborate on:
- The challenge (what problem was being solved, and why was it hard?)
- The approach (how did the team think about it and execute?)
- The result (what was the outcome, measured or implied?)

Note: If the story is very brief (under 100 words for the challenge/approach/result), ask for more detail before proceeding.

**Q6 — Blog Type**
What type of content do you want to create?
a) Industry — north-star narrative with industry trends, competitor context, external research
b) Use-Case Driven — technical/strategic narrative focused on implementation and outcomes
c) Use-Case with Platform Focus — same as use-case but with a named platform (Drupal/HubSpot/Acquia/AWS/Salesforce) at the center

**Q7 — Additional Context**
Provide any additional meeting notes, documents, Slack threads, or supporting details that can enrich this story. (Optional but strongly recommended for Tier 1)

---

## STEP 3: STORY CLASSIFICATION

After receiving all answers, classify the story into Tier 1, 2, or 3 using the tier-classification skill. Show:
- The recommended tier
- Plain-language justification (2-3 sentences)
- What content this tier produces

Then ask: "Does this tier feel right, or would you like to adjust it?" Wait for confirmation before proceeding.

---

## STEP 4: CONTENT CREATION BY TIER

### If Tier 1 — Blog + Distribution Strategy

**Step 4a: Suggest blog topics**
Generate 3 relevant topic options based on the story, theme, and audience. Recommend one with justification. Ask the user to choose.

**Step 4b: Produce outline**
Once topic is chosen, produce a full blog outline:
- Working headline
- Section headings with 1-line description of each section's purpose
- Estimated word count per section
- Key points to address

Ask: "Does this outline work, or would you like changes?" Wait for approval.

**Step 4c: Ask depth questions**
Based on the engagement theme and blog type, generate targeted questions for missing detail. These questions must be specific to the story — not generic. Group by stakeholder type. Wait for answers.

**Step 4d: Write the full blog**
Using the blog-writing skill:
- Minimum 1,500 words
- Paragraph-heavy — avoid excessive lists
- Match tone to the target audience
- Follow the approved outline exactly
- Include headline options, meta description, excerpt, and CTA options
- Reference https://www.axelerant.com/success-stories for relevant case study links where appropriate
- Remove all client names — use anonymized descriptors

### If Tier 2 — Distribution Strategy Only

Produce:
- A focused narrative summary (400-600 words) suitable for distribution
- A LinkedIn post
- A newsletter blurb
- Recommended distribution channels and sequence

### If Tier 3 — LinkedIn Post Only

Produce:
- 2 LinkedIn post variants with different hooks
- Hashtag recommendations
- Best time/context to post

---

## STEP 5: TIER 1 DISTRIBUTION ASSETS

If Tier 1: After the user confirms the blog draft is approved by the marketing team, ask them to confirm it is the edited/final version. Then run the distribution-agent to produce all channel assets.

Shared rules throughout:
- Never expose client names in any output
- Prefer incompleteness over fabrication — if something is unclear, ask
- Match content depth to the classified persona
- Keep all outputs aligned to Axelerant's themes: Strategy, Design, Build, Grow, Delivery
