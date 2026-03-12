# Signal Detection Patterns — Reference

Detailed guide for recognizing, scoring, and categorizing story signals across all four engagement sources. Used by the Story Signal Fetcher when scanning HubSpot, Granola, Slack, and Google Drive.

---

## Signal Scoring Framework

Assign a confidence score (1–10) to every candidate signal. Only surface candidates scoring 4 or above.

### Score Definition

| Score | Meaning | Action |
|-------|---------|--------|
| 8–10 | Strong signal — clear problem, outcome, and approach visible | Surface immediately as Candidate Story Card |
| 6–7 | Moderate signal — key elements present but one or more gaps | Surface with gap flags noted |
| 4–5 | Weak signal — interesting fragment, needs more context | Surface as low-priority candidate |
| 1–3 | Noise — generic, administrative, or purely internal | Discard |

---

## Pattern 1: Problem → Resolution Arc

**What it looks like**: A problem is raised (in a call, Slack thread, or HubSpot note), then a later entry shows it was resolved, fixed, or worked around.

**How to detect it**:
- Multiple entries from the same engagement over time on the same topic
- Escalation followed by resolution: "this is blocking us" → weeks later "unblocked — here's how"
- Language shift from uncertainty to confidence: "we need to figure out X" → "X is done, here's the approach we used"
- Tickets, issues, or risks that are opened and closed with notes

**Source-specific signals**:
- Granola: Kickoff call discusses a risk → Retrospective discusses how the risk was managed
- Slack: Thread opens with a problem question → Final reply confirms resolution
- HubSpot: Deal note flags a delivery concern → Later note marks it resolved with outcome
- Drive: An ADR or decision record describes alternatives considered before a choice was made

**Confidence boost factors**: Specific outcome mentioned (+2), metrics cited (+2), multiple sources corroborate (+1)

**Story potential**: High — this is the fundamental narrative arc of every great case study

---

## Pattern 2: Repeated Discussion of Same Challenge

**What it looks like**: The same topic, problem, or theme surfaces multiple times across different sources or over an extended period.

**How to detect it**:
- The same word or phrase cluster appears in Slack + Granola + HubSpot for the same engagement
- Multiple team members reference the same challenge independently
- The topic appears in different meeting types: kickoff mentions it, status reviews return to it, retrospective explains how it ended

**Cross-source corroboration scoring**:
- Signal appears in 2 sources: +1 to base score
- Signal appears in 3 sources: +2 to base score
- Signal appears in 4 sources: +3 to base score

**Story potential**: Medium-High — repeated discussion signals genuine significance, even if individual entries are thin

---

## Pattern 3: Measurable Improvement

**What it looks like**: Specific numbers cited before and after an intervention. Can be performance metrics, timeline improvements, cost reductions, or usage metrics.

**How to detect it**:
- Numbers with units in proximity to qualitative change language: "from 8 seconds to 1.2 seconds load time", "traffic up 3x", "reduced effort from 4 hours to 20 minutes"
- Comparison language: "before we did X / after we did X", "previously / now", "used to take / now takes"
- Client quotes about improvement: "the client mentioned response time was dramatically better"

**Important**: Approximate or implied metrics still count. "Cut the timeline significantly" with enough context is still surfaceable — flag it as needing a number from the stakeholder.

**Story potential**: High — measurable improvement is the single highest-value evidence type for external storytelling

---

## Pattern 4: Architecture or Design Tradeoff

**What it looks like**: Two or more options were considered, one was chosen, and the reasoning is documented or discussable.

**How to detect it**:
- Decision language: "we went with X instead of Y because...", "we considered Z but ruled it out because..."
- Architecture Decision Records (ADRs) in Drive
- Granola calls with "alternatives considered" or "here's why we chose" moments
- Slack threads debating technical approaches that end with a decision

**Why this matters for content**: The "why behind the what" is the most credible signal of expertise. A reader who learns your decision rationale — including what you rejected and why — gains far more than a reader who just sees the outcome.

**Confidence boost factors**: Clear rationale documented (+2), client constraints cited (+1), alternatives named (+1)

**Story potential**: Medium-High — particularly valuable for Use-Case Driven and Use-Case with Platform Focus content angles

---

## Pattern 5: Delivery Innovation

**What it looks like**: A new process, tool, approach, or team structure was used for the first time in this engagement, and there's evidence it worked.

**How to detect it**:
- Language like "first time we tried...", "we developed a new approach for...", "we built an internal tool to..."
- Process improvements that arose mid-engagement: "we had to invent a workflow for X"
- New team configurations, new sprint structures, new handoff protocols
- Internal tooling, automation, or scripts that were built specifically for this engagement

**Story potential**: Medium — delivery innovation stories are most useful for Tier 3 (culture/process) or as supporting evidence in a larger Tier 1 narrative

---

## Pattern 6: Positive Customer Sentiment

**What it looks like**: The client expressed specific, meaningful satisfaction — not just "great work" but something concrete about the outcome, the team, or the experience.

**How to detect it**:
- Direct quotes from clients in Granola transcripts or HubSpot notes
- Language flagging client reaction: "the client said...", "the stakeholder mentioned...", "their CTO called out..."
- Expansion signals: "the client asked about next phases", "they introduced us to another team", "they extended the engagement"
- Unsolicited praise in email threads or Slack messages

**Important distinction**: Generic positive sentiment ("great to work with") scores 3-4. Specific outcome-based validation ("they told us the migration went faster than any previous vendor delivered") scores 7+.

**Story potential**: Medium-High — client voice is the most credible external validation; direct quotes significantly elevate any story

---

## Pattern 7: Launch or Milestone Moment

**What it looks like**: A significant project moment — go-live, handoff, first-90-days review, successful load test, production deployment.

**How to detect it**:
- Milestone language: "we're live", "went live this morning", "launched successfully", "handoff complete"
- Celebration signals in Slack: 🎉 🚀 ✅ emoji reactions, high reply counts, team mentions
- Granola calls titled "launch review", "go-live debrief", "handoff call"
- HubSpot deal stage changes to "Delivered" or "Closed Won" with notes

**Context to collect**: What was the timeline? Were there risks managed? What was the client's reaction? These answer questions that take a launch from a vanity moment to a real story.

**Story potential**: Medium — launches signal completion, but the story is usually in the complexity overcome to get there

---

## Pattern 8: Technical Breakthrough

**What it looks like**: A novel, non-obvious solution was found to a known or recurring problem in the domain.

**How to detect it**:
- Language expressing surprise or pride: "no one had done this before", "we figured out a way to...", "finally solved the X problem"
- Technical specificity about an unexpected approach: a non-standard architecture decision, a clever use of platform features, an original integration approach
- A solution that took multiple failed attempts before it worked
- Something that would be educationally useful to a peer — another engineer, another CTO — reading about it

**Story potential**: High — technical breakthroughs are the gold standard for Use-Case Driven content; they demonstrate Axelerant's intellectual depth in a way no positioning statement can

---

## What NOT to Surface

Do not create Candidate Story Cards for the following, regardless of source:

- **Pure administrative signals**: Invoice sent, contract signed, call rescheduled, onboarding document shared — unless these coincide with a substantive outcome note
- **Generic positive moments without specificity**: "Great call today", "Really enjoyed working with this team", "Looking forward to Phase 2" — surface only if accompanied by a specific outcome
- **Internal-only discussions with no external relevance**: Team logistics, internal planning debates that don't surface an insight relevant to clients or prospects
- **Any signal scoring below 4**: Thin evidence produces thin content; weak stories damage credibility more than no content

---

## Candidate Story Card Format

When a signal is detected, produce a card in this format:

```
CANDIDATE STORY CARD
══════════════════════════════════════════════════════
Signal ID: [CE-YYYYMMDD-NNN]
Source: [HubSpot / Granola / Slack / Google Drive]
Engagement: [client descriptor — no real names]
Date Range: [when the signal spans]

SIGNAL TYPE: [Pattern name from above]
CONFIDENCE SCORE: [4–10]

CORE SIGNAL
[2-3 sentences describing exactly what was detected]

RAW EVIDENCE SNIPPET
[Brief quote or paraphrase from source — not more than 2-3 lines]

GAPS IDENTIFIED
[What is missing that would strengthen this signal?]

STORY POTENTIAL
[High / Medium-High / Medium / Low]

RECOMMENDED NEXT ACTION
[Route to Story Intelligence] / [Flag for stakeholder question] / [Hold for corroboration]
══════════════════════════════════════════════════════
```

---

## Multi-Source Corroboration Map

When the same engagement surfaces signals across multiple sources, map them before routing to Story Intelligence.

```
CORROBORATION MAP
Engagement: [descriptor]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
HubSpot: [signal summary] — [date]
Granola:  [signal summary] — [meeting title / date]
Slack:    [signal summary] — [channel / date]
Drive:    [signal summary] — [document title / date]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Corroboration Score Adjustment: +[n] (n sources)
Final Confidence Score: [original + adjustment]
```

Corroborated signals should be routed to Story Intelligence as a bundle — not as four separate cards.
