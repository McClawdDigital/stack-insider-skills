---
type: okf-bundle
okf_version: "0.1"
title: "Lindy AI Agent Playbook"
description: "An authoritative guide to Lindy AI — an autonomous AI executive assistant for inbox, meetings, calendar, and follow-ups — sourced from official documentation at docs.lindy.ai and the Lindy blog at lindy.ai/blog."
author: "Stack Insider"
url: "https://bundledex.net/bundles/lindy-ai-agent-playbook"
version: "2.0.0"
tags:
  - lindy
  - ai-agents
  - automation
  - workflow
  - no-code
  - productivity
  - ai-assistant
  - email-automation
  - scheduling
complementary_skills:
  - id: zapier
    description: "Connect Lindy to thousands of apps via Zapier for extended automation reach"
  - id: make
    description: "Advanced scenario building with Lindy as a module in complex multi-step automations"
  - id: notion-api
    description: "Feed Lindy-processed data into structured Notion databases for knowledge management"
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

# Lindy AI Agent Playbook — Official Source Richer Bundle

> **Sourced from official docs (docs.lindy.ai) and blog (lindy.ai/blog). Last ref: July 2026.**

## 1. Official Documentation Reference

- **Primary Docs**: https://docs.lindy.ai/ — hosted on Mintlify, full LLM export at /llms-full.txt
- **What is Lindy?**: https://docs.lindy.ai/ — "One AI assistant for your inbox, meetings, calendar, and follow-ups"
- **Quickstart**: Available at https://docs.lindy.ai/quickstart
- **Best Practices**: https://docs.lindy.ai/ — includes delegation strategies, filter setup, model selection
- **Team Setup**: https://docs.lindy.ai/ — multi-account, workspace, and team billing docs
- **Email Triage**: https://docs.lindy.ai/ — "Sorts, labels, and prioritizes your inbox"
- **Email Drafting**: https://docs.lindy.ai/ — "AI-drafted replies land in your drafts folder"
- **Meeting Prep**: https://docs.lindy.ai/ — "Pre-meeting briefings with attendee research, past context, and agenda"
- **Meeting Notes**: https://docs.lindy.ai/ — recording, transcription, and action item extraction
- **Smart Scheduling**: https://docs.lindy.ai/ — "Finds times, sends invites, and locks in meetings"
- **iMessage & SMS**: https://docs.lindy.ai/ — delegate via text, no app needed
- **Ad Hoc Tasks**: https://docs.lindy.ai/ — research, knowledge bank lookups, reminders
- **Usage & Limits**: https://docs.lindy.ai/ — credit system explained: 1-3 credits basic, ~10 for large models
- **Security**: https://docs.lindy.ai/ — SOC 2, data encryption, access controls
- **Changelog**: https://docs.lindy.ai/ — version history and feature updates
- **Export Docs for LLM**: https://docs.lindy.ai/llms-full.txt (raw markdown of all docs — 16K+ lines)

> Note: Lindy docs are a Single Page App (SPA). Individual doc pages load via JS routing from the main domain.

## 2. Official Blog Posts

Source: https://www.lindy.ai/blog — 533+ articles across categories: Agents, AI Assistants, AI Email Management, AI in Sales, AI Tools

Key posts relevant to Lindy usage:

- **"The 17 Best AI Platforms in 2026 – Tested & Reviewed"** (Jul 15, 2026) — Lindy ranked among top AI platforms
- **"8 Best AI Agents for Sales in 2026"** (Jul 16, 2026) — Lindy's sales agent capabilities
- **"Delegation Matrix: How to Decide What to Delegate First"** (Jul 16, 2026) — Practical framework for Lindy task delegation
- **"I Tested the Top 9 AI Automation Platforms in 2026"** (Jul 16, 2026) — Lindy vs. alternatives comparison
- **"Top 10 AI Agent Frameworks (2026): Expert-Tested & Reviewed"** (Jul 16, 2026) — Lindy's agent framework architecture
- **"11 AI Lead Generation Tools to Close More Deals in 2026"** (Jul 16, 2026) — Lindy for lead gen workflows
- **"How to Automatically Forward Emails in Outlook (+ Fixes)"** (Jul 16, 2026) — Email automation guide
- **"15+ AI Personal Assistants Tested, These Are My Top 10"** (Jul 16, 2026) — Lindy as top AI personal assistant

Categories: Announcements, Agents, AI Email Management, Product Management, AI in Customer Support, AI in HR, Chatbots, Knowledge Management, AI in Sales, AI Assistants, Medical Dictation, AI Tools

## 3. Core Concepts (from Official Docs)

### What Lindy Is
Lindy is an **autonomous AI executive assistant** — not a copilot. It acts independently:
- "Lindy doesn't assist. It acts. Every email answered. Every meeting prepped. Every follow-up sent."
- Replaces 5+ separate tools: email triage, scheduling, meeting notes, follow-ups, task management
- Learns preferences, tone, and priorities over time — "Lindy understands you"
- Accessible via iMessage, SMS, Slack, email, or web app
- Setup time: "2 minutes"

### Key Capabilities
1. **Email Triage** — Sorts, labels, prioritizes inbox autonomously
2. **Email Drafting** — AI drafts in user's voice, lands in drafts folder
3. **Meeting Prep** — Research attendees, past context, agenda
4. **Meeting Notes** — Record meetings, extract action items
5. **Smart Scheduling** — Find times, send invites, avoid back-and-forth
6. **Daily Brief** — Morning summary of what happened overnight
7. **Follow-ups** — Automated follow-up after meetings
8. **Ad Hoc Tasks** — Research, knowledge recall, reminders
9. **iMessage & SMS** — Text-based delegation from phone

### Credit System
- Most tasks: **1-3 credits** on basic models
- Complex tasks: **~10 credits** on large models
- Every task is minimum 1 credit
- Credits consumed by: model intelligence, task complexity, premium actions, agent duration
- **No rollover** between billing cycles
- Overages charged at **2x standard rate**

### Pricing Plans
- Plus, Pro, Max tiers (per-seat monthly)
- Team plans: invite members, share billing, allocate credits per member
- Workspace roles: Owner (full control), Admin (manage team), Member (standard)

### Multi-Account Setup
- Connect multiple Google and Outlook accounts
- Manages email, calendar, and contacts across all accounts simultaneously
- Disconnect from Settings → Integrations

## 4. API Reference

Lindy does not currently expose a public REST API. The product is accessed through:
- **Web App**: https://chat.lindy.ai
- **Chrome Extension**: Coming soon (Gmail first, then Outlook)
- **iMessage/SMS**: Phone-based text delegation
- **Email**: Forward/CC Lindy at your Lindy email address

For integration, Lindy connects natively to:
- **Google Workspace** (Gmail, Calendar, Contacts)
- **Microsoft 365** (Outlook, Calendar, Contacts)
- **Slack** (messaging and delegation)
- **Zapier** (5,000+ app integrations via webhook)

**Data Export**: Full docs available in markdown at https://docs.lindy.ai/llms-full.txt

## 5. Integration Patterns

### Google Workspace Integration
- Connect via OAuth in Settings → Emails / Meetings
- Lindy reads email, calendar, contacts across all connected accounts
- Drafts appear in Gmail drafts folder

### Microsoft 365 Integration
- Same OAuth flow as Google
- Supports Outlook email, calendar, contacts
- Works simultaneously alongside Google accounts

### Slack Integration
- Delegate tasks via Slack DMs with Lindy
- Receive briefs, reminders, and updates in Slack

### Multi-Tool Chaining
Lindy replaces separate tools — no IFTTT-style chaining needed for native features:
- Email → Calendar → Meeting Prep → Notes → Follow-ups (autonomous chain)
- For external apps: use Zapier/Make to trigger Lindy or receive Lindy outputs

## 6. Agent Integration (MCP, Hermes)

### For AI Agents Consuming this Bundle
This bundle is structured as an OKF (Open Knowledge Format) bundle for AI consumption. Keys to know:

- **Lindy's core value**: autonomous execution, not assistance
- **No public API** means agent-to-agent chaining requires Zapier/Make as intermediary
- **Docs are exportable**: Full LLM-optimized markdown at /llms-full.txt
- **Best practice for agents**: Lindy works best as a delegated executor — send it tasks via text, don't try to orchestrate it programmatically

### Suggested MCP Integration
- Use Lindy's Slack integration for agent-to-agent communication
- Chain through Zapier MCP: Lindy → Zapier → other tools
- For Hermes agents: delegate email/scheduling tasks to Lindy via natural language

## 7. Official Learning Path

1. **Start**: Sign up at https://lindy.ai → 2-minute setup
2. **Connect Accounts**: Gmail/Outlook OAuth
3. **Configure Triaging**: Set email triage preferences
4. **Test Delegation**: Text Lindy any task via iMessage/SMS
5. **Advanced**: Build custom workflows (when available in workflow editor)
6. **Team**: Invite team members, set credit allocations
7. **Optimize**: Switch models, set filters, clear context to reduce credit usage

**Support**: support@lindy.ai
**App**: https://chat.lindy.ai
**Security**: SOC 2 compliant, data encrypted at rest and in transit

---

**License:** MIT
**Source material last verified:** July 2026
**BundleDex:** https://bundledex.net/bundles/lindy-ai-agent-playbook