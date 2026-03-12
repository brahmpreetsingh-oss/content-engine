---
description: Organize approved content into a distribution calendar
allowed-tools: Task, Read, Write
argument-hint: [time period: e.g. "Q2 2026" or "next 4 weeks"] [optional: focus area e.g. "HubSpot" or "associations"]
---

Organize approved content into a structured distribution calendar for the period specified in $ARGUMENTS.

## STEP 1: Gather Available Content

Ask the user to provide or confirm the list of content assets that are approved and ready for scheduling. For each piece, collect:
- Content title/topic
- Tier (1/2/3)
- Target persona
- Platform focus or industry vertical (if any)
- Content type (blog / LinkedIn post / newsletter / campaign / etc.)
- Current status (approved / pending approval / needs creative)

## STEP 2: Assess Content Mix

Evaluate the content mix against the recommended tier ratio:
- Target: ~10 Tier 3 : ~5 Tier 2 : ~1-2 Tier 1 per month
- Note any gaps or imbalances
- Flag if too many pieces target the same persona or platform

## STEP 3: Build the Calendar

Distribute content across the specified time period following these principles:
- Space Tier 1 blogs at least 2-3 weeks apart to allow full distribution cycle
- Tier 3 social posts can run 2-3x per week
- Alternate between platform-focused and industry-focused content
- Ensure newsletter schedule aligns with regular send cadence
- LinkedIn posts should not all target the same persona back-to-back
- Allow time after each Tier 1 publish for the sales enablement and platform POC handoffs

## STEP 4: Present the Calendar

Output the calendar in a clean table format:

```
CONTENT CALENDAR — [PERIOD]
═══════════════════════════════════════════════════════════
Date        | Content                    | Type         | Channel       | Status
────────────|────────────────────────────|──────────────|───────────────|────────
[date]      | [title/topic]              | [Tier 1 Blog]| Blog publish  | Approved
[date]      | [LinkedIn post]            | [Tier 3]     | LinkedIn      | Needs creative
[date]      | [newsletter blurb]         | [Tier 1 dist]| Newsletter    | Approved
...
═══════════════════════════════════════════════════════════
```

Also produce:
- **Content mix summary**: How many Tier 1/2/3 pieces, what personas covered, what platforms/industries featured
- **Gaps and recommendations**: What content types or personas are underrepresented
- **Creative dependencies**: Which pieces need visual assets from the Creative plugin before publishing
- **Approval dependencies**: Which pieces are still pending approval

## STEP 5: Export

Offer to produce the calendar as a structured document for sharing with the team.

## Rules
- Only schedule approved or near-approved content — do not speculate about what might be ready
- Flag creative dependencies clearly so nothing stalls at publish time
- Keep the calendar realistic — do not over-schedule and create pressure that degrades content quality
