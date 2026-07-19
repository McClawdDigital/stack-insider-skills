---
type: okf-bundle
okf_version: "0.1"
title: "Gamma AI Presentation Workflow"
description: "An authoritative guide to Gamma — the AI-native presentation tool for creating presentations, documents, and webpages from prompts. Sourced from the official Gamma Help Center (help.gamma.app) and gamma.app."
author: "Stack Insider"
url: "https://bundledex.net/bundles/gamma-ai-presentation-workflow"
version: "2.0.0"
tags:
  - gamma
  - presentations
  - ai-presentations
  - prompt-engineering
  - brand-compliance
  - design
  - slide-decks
  - ai-content
  - documents
  - webpages
complementary_skills:
  - id: canva
    description: "Enhance Gamma-created slides with Canva's design assets and templates"
  - id: google-slides
    description: "Export Gamma presentations to Google Slides for team collaboration"
  - id: figma
    description: "Design custom brand assets in Figma and import into Gamma"
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

# Gamma AI Presentation Workflow — Official Source Richer Bundle

> **Sourced from official Gamma Help Center (help.gamma.app). Last ref: July 2026.**

## 1. Official Documentation Reference

- **Help Center**: https://help.gamma.app/en/ — Intercom-hosted knowledge base
- **Gamma.app**: https://gamma.app (behind Cloudflare WAF — direct browsing limited)
- **Blog**: https://gamma.app/blog (behind Cloudflare — content not directly accessible via browser automation)

**Help Center Collections (11 total, ~110 articles):**

| Collection | Articles | Slug |
|------------|----------|------|
| Gamma Basics | 13 | gamma-basics |
| Editing, Designing & Formatting | 20 | editing-designing-formatting-in-gamma |
| AI Content & Image Generation | 12 | ai-content-image-generation |
| Sharing, Collaboration & Analytics | 8 | sharing-collaboration-analytics |
| Websites & Publishing | 11 | websites-publishing |
| Connectors, Imports & Embeds | 8 | connectors-imports-embeds |
| Accounts, Workspaces & User Settings | 14 | accounts-workspaces-user-settings |
| Subscription & Billing | 12 | subscription-billing |
| Security & Privacy | 3 | security-privacy |
| Troubleshooting | 7 | troubleshooting |
| Tips from our Community Users | 2 | tips-from-our-community-users |

**Key Articles (from Help Center landing page):**
- How do I create a new presentation, document, or webpage in Gamma?
- Where do I start when adding content in Gamma?
- Introduction to the Gamma Dashboard
- What are cards in Gamma and how to do they work?

## 2. Official Blog Posts

Note: gamma.app/blog is behind Cloudflare WAF. Blog content could not be scraped directly.

Based on the site structure and the Help Center, Gamma publishes content on:
- AI presentation best practices
- Prompt engineering tips
- Brand guide setup
- Template showcase
- Community user tips

**Source**: The "Tips from our Community Users" collection (2 articles) at https://help.gamma.app/en/collections/14524045-tips-from-our-community-users

## 3. Core Concepts (from Official Help Center)

### What Gamma Is
Gamma is an **AI-native content creation platform** for presentations, documents, and webpages. Key differentiators:
- **AI-first**: Generate complete decks from prompts or outlines — not just slide templates
- **Multi-format**: Create presentations, documents, or webpages from the same interface
- **Card-based**: Content is organized in cards — Gamma's fundamental content unit
- **No design skills needed**: AI handles layout, visuals, and structure

### Core Concepts

#### Cards
- **Cards** are Gamma's fundamental building block — each card is a discrete content unit
- Cards can contain: text, images, videos, embeds, charts, code blocks
- Cards are arranged vertically and can be reordered, grouped, or styled
- Cards auto-adapt to different formats (presentation → document → webpage)

#### AI Content Generation
- Generate presentations from a single prompt
- Generate from existing documents (paste outline or text)
- AI image generation built in
- Prompt-based slide creation with structure suggestions

#### Brand Kits & Styling
- Custom themes with brand colors, fonts, and logos
- Apply brand kit to any presentation
- Consistent styling across all cards
- Template reuse

#### Dashboard
- Central hub for managing all your Gamma creations
- Organize by workspace, folder, or recent activity
- Quick-create button for new presentations/documents/webpages

#### Import & Export
- Import from: Markdown, Google Docs, URLs
- Export to: PDF, PPTX, Google Slides
- Embed options for webpages

#### Sharing & Collaboration
- Share via link with view/edit permissions
- Real-time collaboration
- Analytics on views and engagement (for published content)
- Comments and feedback

## 4. API Reference

Gamma's public API is not fully documented in the freely available Help Center. Based on platform structure:

- **Export API**: Generate PDF/PPTX for programmatic download
- **Embed API**: Embed Gamma presentations on external websites
- **Import API**: Import content from Markdown, Google Docs
- **Authentication**: Likely OAuth or API key-based

For full API docs: check in-app API settings or contact Gamma support.

## 5. Integration Patterns

### Import Sources (from Help Center)
- **Markdown**: Import structured markdown → Gamma generates cards
- **Google Docs**: Direct import from Google Docs
- **URL**: Paste a URL → Gamma generates content from webpage
- **Clipboard**: Paste text directly → converts to cards

### Export Destinations
- **PDF**: Download as PDF for offline viewing/printing
- **PPTX**: Export to PowerPoint format
- **Google Slides**: Convert for Google Workspace collaboration
- **Embed**: iframe embed for websites
- **Share Link**: Direct URL sharing

### Connectors (from Help Center "Connectors, Imports & Embeds" collection — 8 articles)
- YouTube video embeds
- Figma embeds
- Loom embeds
- Code embeds
- Charts and data visualization embeds

### Collaboration Patterns
- Real-time collaborative editing
- Share with view-only or edit permissions
- Workspace-based organization for teams
- Activity feed and version history

## 6. Agent Integration (MCP, Hermes)

### For AI Agents
- **Programmatic creation**: Use Gamma's import capabilities (Markdown) for agent-to-agent content creation
- **AI agent workflow**: Agent writes markdown → agent imports to Gamma → agent exports PDF
- **MCP potential**: Gamma could be exposed as an MCP tool for presentation generation
- **Hermes integration**: Generate markdown outlines in Hermes, pipe to Gamma for visual rendering

### Suggested Agent Workflows
1. **Research → Presentation**: Agent researches topic → writes structured markdown → imports to Gamma
2. **Meeting → Summary Deck**: Agent takes meeting notes → formats as Gamma cards
3. **Blog → Slide Deck**: Agent converts blog post → markdown → Gamma presentation

## 7. Official Learning Path

1. **Sign Up**: Create account at gamma.app
2. **Dashboard Tour**: Read "Introduction to the Gamma Dashboard" article
3. **First Creation**: Create a new presentation using a prompt
4. **Learn Cards**: Read "What are cards in Gamma" article
5. **Add Content**: Follow "Where do I start when adding content" guide
6. **Style with Brand Kit**: Set up brand colors, fonts, and logos
7. **Collaborate**: Share with team, set permissions
8. **Publish**: Export or publish as webpage
9. **Advanced**: Explore AI image generation, embeds, and connectors

**Help Center**: https://help.gamma.app/en/
**App**: https://gamma.app
**Languages**: 12 languages supported in Help Center

---

**License:** MIT
**Source material last verified:** July 2026
**Note:** gamma.app is behind Cloudflare WAF limiting direct access. Help Center (Intercom-hosted) was the primary source.
**BundleDex:** https://bundledex.net/bundles/gamma-ai-presentation-workflow