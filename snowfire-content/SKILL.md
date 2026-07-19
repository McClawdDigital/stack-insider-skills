---
name: snowfire-content
description: "Assemble brand-compliant, personalized content at scale with Snowfire AI — build modular content blocks, apply brand rules, and assemble dynamic documents for any audience or channel."
tags: [snowfire, content-creation, brand-management, personalization, modular-content, content-assembly]
category: creative
created: 2026-07-19
---

# Snowfire AI Content Assembly

Assemble brand-compliant, personalized content from modular blocks using Snowfire AI, orchestrated from Hermes. This skill covers brand kit setup, block creation, personalization rules, assembly workflows, and multi-channel distribution.

## Trigger Conditions

Use this skill when the user asks to:
- Create brand-compliant content at scale
- Build reusable content components from source material
- Personalize content for different audiences or channels
- Assemble complete documents from modular blocks
- Distribute assembled content via API to multiple platforms

## API Access

Snowfire provides a REST API. Store your API key in Bitwarden:

```bash
# Retrieve Snowfire API key
bw get notes "Snowfire API Key"
```

Base URL: `https://api.snowfire.io/v1`

## Common Operations

### Create Content Block

```bash
curl -X POST "https://api.snowfire.io/v1/blocks" \
  -H "Authorization: Bearer *** \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Product Hero Description",
    "type": "text",
    "content": "{{product_name}} helps {{target_audience}} achieve {{benefit}} with {{key_feature}}.",
    "brand_kit_id": "bk_xyz789",
    "tags": ["product", "hero", "template"]
  }'
```

### Set Brand Rules

```bash
curl -X POST "https://api.snowfire.io/v1/brand-kits" \
  -H "Authorization: Bearer *** \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Corporate Brand 2026",
    "tone": "professional",
    "disallowed_terms": ["cutting-edge", "synergy", "game-changer"],
    "required_sections": ["value_proposition", "call_to_action"],
    "style_guide_url": "https://brand.company.com/style-guide"
  }'
```

### Assemble Document

```bash
curl -X POST "https://api.snowfire.io/v1/assembly" \
  -H "Authorization: Bearer *** \
  -H "Content-Type: application/json" \
  -d '{
    "document_type": "product_description",
    "blocks": [
      {"block_id": "blk_hero", "order": 1},
      {"block_id": "blk_features", "order": 2},
      {"block_id": "blk_cta", "order": 3}
    ],
    "context": {
      "product_name": "DataFlow Pro",
      "target_audience": "data engineers",
      "benefit": "50% faster pipeline deployment",
      "key_feature": "one-click cloud integration"
    },
    "brand_kit_id": "bk_xyz789"
  }'
```

### List Available Blocks

```bash
curl -s "https://api.snowfire.io/v1/blocks" \
  -H "Authorization: Bearer *** | jq '.data[] | {id, name, type, tags}'
```

### Export Assembled Content

```bash
curl -X POST "https://api.snowfire.io/v1/assembly/{assembly_id}/export" \
  -H "Authorization: Bearer *** \
  -H "Content-Type: application/json" \
  -d '{
    "format": "html",
    "include_styles": true
  }'
```

## Workflow Pattern

### Content Assembly Pipeline

1. **Define brand kit** — Set tone, disallowed terms, required sections
2. **Create blocks** — Build reusable content components with variable placeholders
3. **Prepare context data** — Gather product info, audience segments, channel requirements
4. **Assemble documents** — Combine blocks with context for each audience/channel
5. **Review & validate** — Check brand compliance, personalization accuracy
6. **Distribute** — Push to CMS, marketing platform, or API endpoint

## Environment Setup

```bash
export SNOWFIRE_API_KEY=*** SNOWFIRE_DEFAULT_BRAND_KIT="bk_xyz789"
```

## Pitfalls

- **Block granularity.** Too coarse → can't mix and match. Too fine → assembly is tedious. Aim for paragraph-level blocks.
- **Variable naming convention.** Use consistent `{{snake_case_variables}}` across all blocks. Document them in a reference file.
- **Brand rule enforcement.** Snowfire flags violations but doesn't auto-fix. Review flagged content before distribution.
- **Context completeness.** Missing context variables produce empty `{{placeholders}}` in output. Validate context before assembly.
- **Version control.** Blocks change over time. Use Snowfire block versioning or maintain a changelog.

## Verification

```bash
# Check brand kits
curl -s "https://api.snowfire.io/v1/brand-kits" \
  -H "Authorization: Bearer *** | jq '.data | length'
# Should return count of available brand kits

# Test block creation
curl -s "https://api.snowfire.io/v1/blocks?limit=1" \
  -H "Authorization: Bearer *** | jq '.data[0] | {id, name}'
```