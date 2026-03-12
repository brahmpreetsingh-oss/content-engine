---
description: Scan engagement sources for story candidates
allowed-tools: Task, Read, Write, mcp__e6177f79-cc82-46f1-b70b-f71067b33a7c__search_crm_objects, mcp__054afba5-16ff-48dd-8246-9e4706c6253e__slack_search_public_and_private, mcp__04132572-a2bc-48fe-8e48-5d26c36335e6__query_granola_meetings, mcp__04132572-a2bc-48fe-8e48-5d26c36335e6__list_meetings, mcp__c1fc4002-5f49-5f9d-a4e5-93c4ef5d6a75__google_drive_search
argument-hint: [client-name-or-project] [optional: time-period e.g. "last 30 days"]
---

Mine engagement sources for story candidates for: $ARGUMENTS

Follow this process exactly:

1. **Parse the input**: Extract the client/project name and any time period from $ARGUMENTS. If no time period is specified, default to the last 30 days.

2. **Search all four sources in parallel**:
   - HubSpot: Search for CRM engagement notes, deal activities, and contact interactions related to the client/project
   - Granola: Search meeting notes and transcripts from the specified time period for this engagement
   - Slack: Search project and client channels for milestone discussions, problem-solving threads, and outcome signals
   - Google Drive: Search for project documents, retrospectives, and delivery notes

3. **Apply signal detection patterns**: For each piece of content found, look for:
   - Technical breakthroughs or non-obvious problem solutions
   - Delivery rescues or risk-to-recovery moments
   - Significant design or architecture decisions with tradeoffs
   - Measurable performance gains or KPI improvements
   - Platform migration lessons
   - Stakeholder alignment wins
   - Process innovations
   - Customer praise or strong outcome signals
   - Launch milestones or first-90-days reflections

4. **Score each candidate**: Assign a confidence score 1-10 based on:
   - Strength of the signal (how clear is the story?)
   - External relevance (would Axelerant's ICP care about this?)
   - Evidence quality (is it fact or speculation?)
   - Uniqueness (does this differentiate Axelerant?)

5. **Produce Candidate Story Cards**: For every signal scoring 4 or above, produce a Candidate Story Card using the story-signal-fetcher agent format. Discard anything scoring below 4 with a brief note on why.

6. **Present summary**: After producing all cards, show:
   - Total signals found
   - Cards produced (with scores)
   - Cards discarded (with reasons)
   - Recommended next action (usually: "run story-intelligence on the top candidates")

Shared rules:
- Anonymize all client-identifying information in outputs
- Do not over-interpret signals — surface as found
- Prefer surfacing weak signals as "needs context" over forcing a story
- Keep each card concise — this is detection, not narration
