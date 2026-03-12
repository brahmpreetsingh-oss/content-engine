---
description: Build a content pack for a specific platform partner
allowed-tools: Task, Read, Write, WebFetch, mcp__e6177f79-cc82-46f1-b70b-f71067b33a7c__search_crm_objects, mcp__04132572-a2bc-48fe-8e48-5d26c36335e6__query_granola_meetings, mcp__c1fc4002-5f49-5f9d-a4e5-93c4ef5d6a75__google_drive_search, mcp__054afba5-16ff-48dd-8246-9e4706c6253e__slack_search_public_and_private
argument-hint: [platform: hubspot|drupal|acquia|aws] [optional: target vertical or use case]
---

Build a complete content pack for the platform specified in $ARGUMENTS.

Supported platforms: HubSpot, Drupal, Acquia, AWS

## STEP 1: Parse Input
Extract the target platform from $ARGUMENTS. If a vertical or use case is also specified, note it as the focus filter.

## STEP 2: Mine Engagement Sources
Search all engagement sources (HubSpot, Granola, Slack, Google Drive) for stories where this platform played a central role:
- Deals and engagements where the platform was the primary technology
- Meeting notes where platform capabilities were discussed
- Delivery docs where the platform implementation is detailed
- Slack threads where platform-specific problems were solved

## STEP 3: Inventory Stories
Produce a list of all found engagement stories related to this platform, with:
- Brief description (2-3 sentences)
- Confidence score as story material
- Suggested tier (1/2/3)
- Suggested content angle (use-case / platform-led / industry)

Ask the user to confirm which stories to include in the pack before writing begins.

## STEP 4: Build the Content Pack
For each confirmed story, produce:

**A. Platform Proof Point** (150-200 words)
Concise narrative of how the platform contributed to the outcome.
Written to be usable in BDR outreach, partner co-marketing emails, or proposal appendices.
Format: Problem → Platform Role → Outcome

**B. Platform-Focused Blog Brief**
If the story is Tier 1 or Tier 2, produce a full blog brief:
- Headline options
- Recommended structure
- Key technical points to cover about the platform
- Recommended CTA (contact for assessment / read case study / etc.)

**C. Co-Marketing Asset**
A 200-word summary written for the platform POC (HubSpot, Acquia, AWS partner manager):
- How Axelerant used their platform to drive client success
- Why this story works for their audience
- How they can use it (joint webinar pitch, newsletter, partner showcase)

**D. LinkedIn Content Brief**
Post concept and copy for a platform-focused LinkedIn post. Include:
- Hook line
- Post body (150-250 words)
- Platform tag suggestion (e.g., @HubSpot, @Acquia)
- Relevant hashtags

## STEP 5: Pack Summary
Present the completed pack with:
- Number of stories included
- Content assets produced
- Recommended distribution sequence for this platform pack
- Handoff note for the platform POC

## Rules
- Remove client names from all outputs unless client has given explicit permission
- Keep platform references factual — do not overclaim platform capabilities
- Every proof point must trace back to an actual engagement, not a general claim
- Flag where more detail is needed before the asset is publishable
