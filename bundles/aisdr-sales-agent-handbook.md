---
type: okf-bundle
okf_version: "0.1"
title: "AiSDR Sales Agent Handbook"
description: "An authoritative guide to AiSDR — an autonomous AI sales development representative platform for outbound sequences across email and LinkedIn. Sourced from official site (aisdr.com), blog, and knowledge base."
author: "Stack Insider"
url: "https://bundledex.net/bundles/aisdr-sales-agent-handbook"
version: "2.0.0"
tags:
  - aisdr
  - sales
  - outbound
  - ai-sales
  - crm
  - lead-generation
  - email-outreach
  - sdr
  - sales-automation
  - linkedin-outreach
complementary_skills:
  - id: hubspot
    description: "Sync AiSDR sequences and lead data with HubSpot CRM"
  - id: lemlist
    description: "Combine AiSDR AI with Lemlist's multichannel cold outreach platform"
  - id: salesforce
    description: "Enterprise CRM integration for AiSDR-managed pipeline"
sections:
  - id: official-docs
    title: "Official Documentation Reference"
    path: sections/01-official-docs.md
  - id: official-blog
    title: "Official Blog Posts"
    path: sections/02-official-blog.md
  - id: core-concepts
    title: "Core Concepts (from Docs)"
    path: sections/03-core-concepts.md
  - id: api-reference
    title: "API Reference"
    path: sections/04-api-reference.md
  - id: integration-patterns
    title: "Integration Patterns"
    path: sections/05-integration-patterns.md
  - id: agent-integration
    title: "Agent Integration (MCP, Hermes)"
    path: sections/06-agent-integration.md
  - id: learning-path
    title: "Official Learning Path"
    path: sections/07-learning-path.md
---

# AiSDR Sales Agent Handbook — Official Source Richer Bundle

> **Sourced from official site (aisdr.com), blog (aisdr.com/blog), and knowledge base. Last ref: July 2026.**

## 1. Official Documentation Reference

- **Website**: https://aisdr.com
- **Blog**: https://aisdr.com/blog
- **Knowledge Base**: https://aisdr.com/knowledge-base (returns 404 — knowledge base may be in-app only)
- **Guides**: https://aisdr.com/guides
- **Resource Library**: https://aisdr.com/resources
- **Pricing**: https://aisdr.com/pricing
- **Case Studies**: https://aisdr.com/case-studies
- **Trust Center**: https://aisdr.com/trust-center
- **"State of AI SDR Industry 2026" report**: Available via blog

> Note: docs.aisdr.com does not resolve. The knowledge base URL returns 404 — documentation is likely behind login. Primary public sources are the blog and guides.

**Key site pages (from footer links):**
- What is AiSDR? / Features / Prospecting with AI
- Independent AI sales agent / End-to-end AI sales outreach
- AI for HubSpot sales / Aircall integration
- AiSDR vs competition
- AiSDR for AI Assistants
- AI Strategist
- AI Prospecting database for Inc 5000 companies

## 2. Official Blog Posts

Source: https://aisdr.com/blog — categorized by: AI in Action, AiSDR news, Blog, Email Frameworks, Expert Insights, GTM Strategy, Leadership Nuggets, Marketing, Sales, Sales Copy Clinic

**Key articles:**

- **"Building a SaaS GTM Strategy: How Modern Marketing Teams Drive Revenue"** (Mar 12, 2026, Josh Schiefelbein) — Go-to-market strategy for SaaS companies using AI SDRs
- **"What Makes AI SDR Implementations Fail (and How to Get It Right)"** (Mar 2, 2026, Valeria Raznatovska) — Why AI SDR rollouts fail and how to rebuild them
- **"The Biggest Challenge to AI SDR Adoption"** (Oct 15, 2025, Yuriy Zaremba) — How AI SDRs outperform people and why most don't see it
- **"AI SDR Showdown: Sales Autopilots vs Sales Copilots"** (Feb 12, 2025, Josh Schiefelbein) — Autopilot vs. copilot approaches for sales outreach

**Featured Report**: "2026 State of the AI SDR Industry Report" — Real data on where AI SDR works, where it breaks, what teams doing differently when they get results

**AI Assistants pages**: AiSDR for AI Assistants (ask ChatGPT, ask Claude, ask Grok about AiSDR)

## 3. Core Concepts (from Official Site)

### What AiSDR Is
AiSDR is an **autonomous AI sales development representative** platform. It deploys AI agents that:
- Research each prospect individually
- Craft personalized email and LinkedIn messages
- Handle replies and objections autonomously
- Book meetings into calendar
- Run multi-step, multi-channel sequences
- All with human oversight and review mode

### Key Capabilities (from site)

#### AI Prospecting
- AI-powered lead research and enrichment
- Prospect database with firmographic and technographic data
- Inc 5000 company prospecting database

#### Personalization Engine
- Researches each prospect before outreach
- Generates personalized icebreakers based on recent activity (funding news, job changes, content published)
- Tailors message tone and content to prospect role and industry
- Adaptive based on reply analysis

#### Multi-Channel Sequences
- **Email**: Automated personalized email sequences
- **LinkedIn**: Connection requests, InMails, profile visit triggers
- **Sequences**: Multi-step with branching logic based on prospect behavior
- **Timing**: Optimal send time based on engagement patterns

#### CRM Integration (from site pages)
- **HubSpot**: Full bidirectional sync — sequences, contacts, deals
- **Salesforce**: Enterprise CRM sync
- **Aircall**: Call logging integration
- Activity logging and pipeline updates

#### Autonomous Operations
- Handles replies autonomously (answers questions, handles objections)
- Books meetings directly into rep's calendar
- Escalates to human when needed
- Review mode for compliance oversight

#### AI Sales Agent Types
- **Independent AI sales agent**: Fully autonomous outbound
- **AI Strategist**: Strategic campaign design
- **End-to-end AI sales outreach**: From prospecting to meeting booked

## 4. API Reference

AiSDR does not have publicly documented API endpoints. Integration is primarily through:
- **Native CRM sync**: HubSpot, Salesforce (bi-directional)
- **Aircall integration**: Call logging
- **Webhooks**: For custom integrations (likely available in-app)
- **Zapier**: Potentially available for no-code integrations

For API access: Contact AiSDR support or check in-app settings.

## 5. Integration Patterns

### HubSpot CRM Integration
- Sync contacts, companies, deals bidirectionally
- Log email and LinkedIn activities to CRM
- Update deal stages based on sequence progress
- Sync meeting bookings to HubSpot calendar

### Salesforce Integration
- Enterprise-grade sync for Salesforce orgs
- Account, contact, lead, and opportunity sync
- Activity logging and campaign attribution

### Aircall Integration
- Log outbound calls
- Sync call recordings and notes
- Trigger call sequences from AiSDR

### Multi-Channel Outreach Pattern
1. Prospect identified and researched
2. LinkedIn touch (connection request + note)
3. Email follow-up sequence (3-5 touches)
4. Reply handling and objection management
5. Meeting booking
6. CRM update

### Human-in-the-Loop Pattern
- Review mode: Human approves messages before sending
- Escalation: Complex replies escalated to human
- Analytics dashboard: Monitor AI performance

## 6. Agent Integration (MCP, Hermes)

### For AI Agents
AiSDR has a dedicated "AiSDR for AI Assistants" page — the platform is designed to be queried by AI assistants (ChatGPT, Claude, Grok). This suggests they support:
- **AI assistant query**: Ask ChatGPT/Claude/Grok about AiSDR capabilities
- **MCP potential**: AiSDR could expose agent capabilities via MCP for sales orchestration

### Suggested AI Agent Workflows
1. **SDR Agent**: AiSDR as autonomous outbound agent → handles full sales development cycle
2. **Lead Enrichment → Outreach**: Enrich leads via AI → activate AiSDR sequence
3. **Reply Analysis**: AiSDR handles replies → AI agent analyzes sentiment and intent
4. **Pipeline Management**: AiSDR books meetings → CRM updates → AI agent manages pipeline

### Hermes Integration
- Delegate outbound sequences to AiSDR from Hermes
- Query AiSDR for pipeline status and sequence analytics
- Orchestrate multi-tool workflows: Lead gen → AiSDR outreach → CRM sync

## 7. Official Learning Path

1. **Read the Report**: Download "2026 State of the AI SDR Industry Report" for baseline understanding
2. **Book a Demo**: See personalized demo at aisdr.com
3. **Define ICP**: Set Ideal Customer Profile parameters
4. **Connect CRM**: Integrate HubSpot or Salesforce
5. **Build First Sequence**: Create multi-step email/LinkedIn sequence
6. **Review & Optimize**: Use analytics to refine messaging and targeting
7. **Scale**: Expand to multiple sequences, teams, and channels

**Resources**: Blog, Guides, Videos, Case Studies, Resource Library
**AI Assistant Pages**: Ask ChatGPT / Claude / Grok about AiSDR
**Contact**: team@aisdr.com

---

**License:** MIT
**Source material last verified:** July 2026
**Note:** docs.aisdr.com does not exist. Knowledge base returns 404. Primary sources are the main site, blog, and guides.
**BundleDex:** https://bundledex.net/bundles/aisdr-sales-agent-handbook