---
name: gamma-presentations
description: "Create AI-powered presentations with Gamma from Hermes — generate slide decks from structured input, enforce brand compliance, and automate bulk presentation creation."
tags: [gamma, presentations, slide-decks, prompt-engineering, brand-compliance, ai-design]
category: creative
created: 2026-07-19
---

# Gamma AI Presentation Workflow

Create stunning, brand-compliant presentations with Gamma AI, orchestrated from Hermes. This skill covers prompt engineering, deck generation, brand kit application, and bulk automation.

## Trigger Conditions

Use this skill when the user asks to:
- Create a presentation from notes, an outline, or raw content
- Enforce brand guidelines on a generated deck
- Batch-generate multiple presentations from structured data
- Export presentations to PDF, PPT, or Google Slides
- Apply brand kits to existing Gamma presentations

## API Access

Gamma provides a REST API. Store your API key in Bitwarden:

```bash
# Retrieve Gamma API key
bw get notes "Gamma API Key"
```

Base URL: `https://api.gamma.app/v1`

## Common Operations

### Generate a Presentation from Outline

```bash
curl -X POST "https://api.gamma.app/v1/presentations/generate" \
  -H "Authorization: Bearer *** \
  -H "Content-Type: application/json" \
  -d '{
    "title": "Q4 Marketing Strategy",
    "outline": [
      {"slide": 1, "type": "title", "content": "Q4 Marketing Strategy"},
      {"slide": 2, "type": "bullets", "content": "Key objectives for Q4"},
      {"slide": 3, "type": "chart", "content": "Budget allocation by channel"}
    ],
    "brand_kit_id": "bk_abc123",
    "format": "widescreen"
  }'
```

### Apply Brand Kit

```bash
curl -X POST "https://api.gamma.app/v1/presentations/{presentation_id}/brand" \
  -H "Authorization: Bearer *** \
  -H "Content-Type: application/json" \
  -d '{
    "brand_kit_id": "bk_abc123",
    "override_colors": true,
    "override_fonts": true
  }'
```

### Export Presentation

```bash
curl -X POST "https://api.gamma.app/v1/presentations/{presentation_id}/export" \
  -H "Authorization: Bearer *** \
  -H "Content-Type: application/json" \
  -d '{
    "format": "pdf",
    "include_notes": false
  }'
```

### List Brand Kits

```bash
curl -s "https://api.gamma.app/v1/brand-kits" \
  -H "Authorization: Bearer *** | jq '.'
```

## Prompt Engineering Tips

### Structured Outline Format

For best results, provide a structured outline with slide types:

- `title` — Opening/cover slides
- `bullets` — Bullet point lists
- `chart` — Data visualizations
- `section` — Section dividers
- `quote` — Pull quotes or testimonials
- `comparison` — Side-by-side comparisons
- `image` — Full-bleed image slides

### Brand Kit Setup

Create brand kits in the Gamma UI first, then reference by ID:

1. Log into Gamma → Brand Kits → Create New
2. Upload logo, set colors (primary/secondary/accent), choose fonts
3. Note the brand kit ID from the URL or API response

## Environment Setup

```bash
export GAMMA_API_KEY="your...xport GAMMA_BRAND_KIT_ID="bk_your_default"
```

## Pitfalls

- **Content length.** Gamma works best with bullet points and short paragraphs, not walls of text. Pre-trim content.
- **Brand kit IDs.** Reusable across presentations. Apply before or after generation, but applying after may cause layout shifts.
- **Export formats.** PPT export may have minor formatting differences vs the Gamma web viewer. Always verify.
- **API rate limits.** Gamma enforces tier-based rate limits. For bulk generation, add delays between requests.
- **Image generation.** Gamma's built-in AI image generation may not match brand style. Upload custom images via assets endpoint.

## Verification

```bash
# List presentations
curl -s "https://api.gamma.app/v1/presentations" \
  -H "Authorization: Bearer *** | jq '.data | length'
```