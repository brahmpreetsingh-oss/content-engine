# Content Engine — Axelerant Marketing Plugin

**Version 0.5.0** — AI-powered content production system that mines engagement signals from HubSpot, Granola, Slack, and Google Drive, then produces use-case, platform, and industry content through a 9-agent pipeline with visual design, automated HubSpot CMS publishing, and Slack-based review workflows.

## What It Does

The Content Engine turns client engagement signals into published blog posts and distribution assets. It operates as a 12-stage pipeline orchestrated by a central agent that dispatches work to specialized sub-agents.

### Pipeline Stages

| # | Stage | Agent | What Happens |
|---|-------|-------|-------------|
| 1 | **detect** | story-signal-fetcher | Scan HubSpot, Granola, Slack, Drive for story signals |
| 2 | **cluster** | orchestrator | Group related signals into story candidates |
| 3 | **understand** | story-intelligence | Build evidence-backed dossier from all sources |
| 4 | **classify** | story-classifier | Assign tier, scope, theme, content angle |
| 5 | **enrich** | question-generator | Generate stakeholder questions if gaps exist |
| 6 | **draft** | narrative-writer | Write the blog post or LinkedIn content |
| 7 | **agent-review** | content-reviewer | Quality-gate the draft with type-aware lens |
| 8 | **review** | orchestrator | Share draft for human review (Brahm approval gate) |
| 9 | **design** | design-agent | Generate feature image and inner diagrams |
| 10 | **hubspot-draft** | orchestrator | Upload images, create HubSpot blog post draft |
| 11 | **wait-for-feedback** | orchestrator | Share in Slack, register in publish queue |
| 12 | **published** | publish-monitor | Auto-publish on reviewer approval |

### Content Tiers

| Tier | Format | Length | Example |
|------|--------|--------|---------|
| Tier 1 | Long-form blog | 1,500+ words | Use-case deep-dive with technical detail |
| Tier 2 | Short blog | 600–1,000 words | Platform-focused insight |
| Tier 3 | LinkedIn post | 200–400 words | Quick take or engagement highlight |

## Agents

| Agent | Model | Purpose |
|-------|-------|---------|
| `orchestrator` | inherit | Pipeline controller — routes work, tracks state, manages HubSpot publishing |
| `story-signal-fetcher` | inherit | Scans sources for candidate story moments |
| `story-intelligence` | opus | Builds full evidence-backed story dossiers |
| `story-classifier` | inherit | Classifies stories into tier, scope, theme |
| `question-generator` | inherit | Generates stakeholder questions for gaps |
| `narrative-writer` | inherit | Writes blog posts and LinkedIn content |
| `content-reviewer` | inherit | Quality-gates drafts before publish |
| `design-agent` | sonnet | Generates Axelerant-branded feature images and diagrams |
| `distribution-agent` | inherit | Creates channel-specific distribution assets |

## Commands

| Command | What It Does |
|---------|-------------|
| `/mine-engagement` | Scan engagement sources for story candidates |
| `/create-content` | Full guided pipeline from signal to published post |
| `/distribute-content` | Create distribution assets from approved content |
| `/content-calendar` | Organize approved content into a calendar |
| `/platform-content-pack` | Build a content pack for a platform partner |
| `/industry-content-pack` | Build a content pack for an industry vertical |

## Skills

| Skill | Purpose |
|-------|---------|
| `blog-writing` | Long-form blog structure, format, and style guide |
| `distribution-briefing` | Distribution asset templates and channel selection |
| `story-mining` | Signal extraction patterns and source scanning |
| `tier-classification` | Tier criteria and classification rubric |

## Knowledge Files

| File | Contents |
|------|----------|
| `axelerant-identity.md` | Brand voice, values, positioning |
| `axelerant-services.md` | Service lines and capability descriptions |
| `buyer-centric-framework.md` | Target personas and buying journey |
| `engagement-themes.md` | Content themes mapped to engagement types |
| `hubspot-publishing.md` | HubSpot CMS config, API patterns, publish queue |

## Required Connectors

These MCP connectors must be enabled in Cowork settings:

| Connector | Used By | Purpose |
|-----------|---------|---------|
| **HubSpot** | signal-fetcher, orchestrator | CRM data scanning + CMS blog publishing |
| **Slack** | signal-fetcher, intelligence, orchestrator | Channel scanning + review workflow |
| **Google Drive** | signal-fetcher, intelligence | Project document retrieval |
| **Granola** | signal-fetcher, intelligence | Meeting transcript access |

## HubSpot CMS Integration

The orchestrator creates blog post drafts in HubSpot and manages the publish lifecycle.

### Architecture

The Cowork VM cannot make outbound HTTPS requests directly (blocked by proxy). All HubSpot API calls route through the `osascript` tool, which runs shell commands on the host machine with unrestricted network access.

```
Orchestrator → osascript → host curl → HubSpot API
```

### Publishing Flow

1. **Design agent** generates feature image + diagrams
2. **Design agent** uploads images to HubSpot Files via osascript curl
3. **Orchestrator** creates blog post draft with `postBody` HTML
4. **Orchestrator** PATCHes the post to attach `featuredImage` URL
5. **Orchestrator** shares draft link + canvas in Slack review thread
6. **Orchestrator** registers post in the publish queue JSON
7. **Publish monitor** (scheduled task) checks Slack threads 3x daily
8. On reviewer approval → publish monitor calls `push-live`

### Publish Queue

Posts awaiting review are tracked in:
```
/Users/brahm/Documents/Claude/Scheduled/content-engine-publish-queue.json
```

The `content-engine-publish-monitor` scheduled task runs at 9am, 1pm, and 5pm to:
- Check Slack review threads for approval signals
- Auto-publish approved posts via HubSpot API
- Send reminder pings after 48 hours with no response
- Flag posts where changes were requested

See `knowledge/hubspot-publishing.md` for full API configuration.

## What's New in v0.5.0

### HubSpot CMS Publishing Pipeline
- Three new pipeline stages: `hubspot-draft`, `wait-for-feedback`, `published`
- Orchestrator creates blog post drafts directly in HubSpot CMS
- Feature images and diagrams uploaded to HubSpot Files
- osascript API bridge pattern for VM→host network access

### Slack-Based Review Workflow
- Draft shared in #content-engine-eng with canvas link + HubSpot preview
- Designated reviewers tagged in thread
- 48-hour review window with auto-reminder
- Explicit approval required — silence ≠ consent

### Auto-Publish System
- Publish queue JSON tracks posts awaiting approval
- Scheduled monitor checks review threads 3x daily
- Auto-publishes on approval, flags change requests

### Agent Updates
- **Orchestrator**: Added `slack_send_message` tool, 3 new pipeline stages, HubSpot CMS integration docs, publish queue management
- **Design Agent**: Fixed hardcoded session paths with dynamic detection, added HubSpot Files upload step, updated output format with CDN URLs
- **Story Intelligence**: Added `slack_search_channels`, `slack_read_canvas`, `get_user_details` tools
- **Story Signal Fetcher**: Added `slack_search_channels`, `slack_read_channel`, `slack_read_canvas`, `slack_read_thread`, `get_crm_objects`, `get_user_details` tools

### New Knowledge File
- `hubspot-publishing.md` — HubSpot portal config, PAT, API endpoints, osascript patterns, publish queue schema, review workflow rules
