---
name: story-mining
description: >
  This skill should be used when scanning or extracting engagement signals
  from HubSpot, Granola, Slack, or Google Drive for content story candidates.
  Triggers when someone asks to "find stories in engagements", "mine meeting
  notes for content", "what stories does this project have", or when the
  story-signal-fetcher agent needs source scanning guidance.
version: 0.1.0
---

# Story Mining — Axelerant Content Engine

Extract meaningful story signals from four engagement sources. The goal is to surface candidate moments — not to write narratives. Detection first, interpretation later.

## The Four Sources

### 1. HubSpot
What to look for:
- Deal notes mentioning outcomes, milestones, or client reactions
- Contact activity logs showing repeated discussion of a challenge
- Engagement activities where a significant deliverable was mentioned
- Stage changes with commentary on what drove the progression
- Notes from discovery calls that reveal client problems in their own words

Search strategies:
- Search by company/contact name for a specific engagement
- Filter for recent activity in the last 30-60 days
- Look for keywords: "delivered", "resolved", "launched", "improved", "challenge", "won"

### 2. Granola (Meeting Transcripts)
What to look for:
- Retrospective calls where outcomes were discussed
- Technical deep-dives where architecture decisions were made
- Client feedback calls where outcomes were validated
- Delivery reviews where risks or blockers were resolved
- Kickoff and strategy sessions where the problem was scoped

Search strategies:
- Search by client name or project name
- Search by time period (last 30 days, last quarter)
- Look for meetings titled: retrospective, review, kickoff, strategy, planning, debrief

What to extract from transcripts:
- Problem statements (usually in the first third of the call)
- Decision moments ("we decided to...", "the reason we went with...")
- Outcome validation ("the client said...", "the result was...")
- Team dynamics that show Axelerant's approach to delivery

### 3. Slack
What to look for:
- Threads where a specific technical challenge was solved collaboratively
- Milestone announcements in project channels
- Client feedback shared by the delivery team
- Problem escalations followed by resolution
- Architecture or design decisions debated and resolved
- Launch moments ("we're live!", "went live this morning")

Search strategies:
- Search project-specific channels (usually named after the client/project)
- Look for threads with high reply counts — these usually indicate significant discussions
- Search for keywords: "resolved", "live", "launched", "fixed", "client loved", "breakthrough"
- Look for emoji reactions that signal significance (✅, 🎉, 🚀)

### 4. Google Drive
What to look for:
- Project retrospective documents
- Delivery reports shared with clients
- Architecture decision records (ADRs)
- Proposal documents that defined the problem scope
- SOW amendments that reflect scope changes due to complexity
- Client-facing outcome summaries

Search strategies:
- Search by client/project name
- Look for document types: retrospective, review, report, ADR, summary, handoff

## Signal Detection Patterns

Apply these patterns across all four sources:

| Pattern | What It Looks Like | Story Potential |
|---------|-------------------|----------------|
| Problem → Resolution arc | Escalation followed by fix, delivery risk followed by recovery | High |
| Repeated discussion of same challenge | Same topic appears in multiple sources over time | Medium-High |
| Measurable improvement | Specific metric cited before/after | High |
| Architecture/design tradeoff | Two options debated, one chosen with reasoning | Medium-High |
| Delivery innovation | A new process or approach used for the first time | Medium |
| Positive customer sentiment | Client expressing strong satisfaction, surprise, or outcome validation | Medium-High |
| Launch/milestone | Go-live moment, handoff, first-90-days reflection | Medium |
| Technical breakthrough | A novel solution to a known problem | High |

## What NOT to Mine

Do not surface these as story candidates:
- Pure administrative signals (invoice sent, call rescheduled, onboarding completed without outcome)
- Generic positive moments without specificity ("great call today")
- Internal-only discussions with no external relevance
- Signals below confidence score 4

## Output Standard

For each signal surfaced, produce a Candidate Story Card. Keep it minimal — the Story Intelligence Agent does the deep reading. Your job is detection, not narration.
