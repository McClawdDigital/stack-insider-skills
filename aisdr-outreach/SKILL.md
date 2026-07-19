---
name: aisdr-outreach
description: "Run AI-powered sales outreach via AiSDR — configure sequences, manage lead lists, personalize at scale, sync with CRM, and monitor campaign performance."
tags: [aisdr, sales, outbound, email-outreach, ai-sales, crm-sync, lead-generation]
category: email
created: 2026-07-19
---

# AiSDR Sales Outreach

Run AI-powered outbound sales sequences with AiSDR, orchestrated from Hermes. This skill covers setup, lead management, sequence configuration, personalization, CRM sync, and performance tracking.

## Trigger Conditions

Use this skill when the user asks to:
- Launch an AI outbound campaign for a target audience
- Configure or update AiSDR sequences
- Import leads and personalize outreach
- Sync AiSDR data with CRM (HubSpot, Salesforce)
- Review campaign performance and iterate

## API Access

AiSDR provides a REST API. Store your API key in Bitwarden:

```bash
# Retrieve AiSDR API key
bw get notes "AiSDR API Key"
```

Base URL: `https://api.aisdr.com/v1`

## Common Operations

### List Campaigns

```bash
curl -s "https://api.aisdr.com/v1/campaigns" \
  -H "Authorization: Bearer *** | jq '.'
```

### Import Leads

```bash
curl -X POST "https://api.aisdr.com/v1/leads/import" \
  -H "Authorization: Bearer *** \
  -H "Content-Type: application/json" \
  -d '{
    "leads": [
      {
        "email": "prospect@company.com",
        "first_name": "Jane",
        "last_name": "Doe",
        "company": "Acme Corp",
        "title": "VP of Engineering",
        "linkedin_url": "https://linkedin.com/in/janedoe"
      }
    ],
    "campaign_id": "camp_abc123"
  }'
```

### Create Sequence

```bash
curl -X POST "https://api.aisdr.com/v1/sequences" \
  -H "Authorization: Bearer *** \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Enterprise Follow-up",
    "steps": [
      {"day": 0, "channel": "email", "template_id": "tpl_001"},
      {"day": 3, "channel": "email", "template_id": "tpl_002"},
      {"day": 7, "channel": "linkedin", "template_id": "tpl_003"}
    ],
    "targeting": {
      "industries": ["saas", "technology"],
      "company_size": {"min": 50, "max": 1000}
    }
  }'
```

### Campaign Performance

```bash
curl -s "https://api.aisdr.com/v1/campaigns/{campaign_id}/stats" \
  -H "Authorization: Bearer *** | jq '.metrics'
```

### Sync to CRM

```bash
curl -X POST "https://api.aisdr.com/v1/integrations/hubspot/sync" \
  -H "Authorization: Bearer *** \
  -H "Content-Type: application/json" \
  -d '{
    "direction": "bidirectional",
    "entity": "contacts",
    "field_mapping": {
      "aisdr_status": "hs_lead_status",
      "aisdr_score": "hs_lead_score"
    }
  }'
```

## Workflow Pattern

### Typical Campaign Launch

1. **Define ICP** — Industry, company size, title, geography
2. **Build list** — Import leads from CSV, Apollo, or ZoomInfo
3. **Create templates** — Write email/LinkedIn templates with personalization variables
4. **Configure sequence** — Set steps, timing, channel mix
5. **Launch campaign** — Activate AiSDR to start outreach
6. **Monitor** — Track opens, replies, meetings booked
7. **Iterate** — A/B test templates, adjust targeting, refine sequencing

## Environment Setup

```bash
export AISDR_API_KEY=*** AISDR_WEBHOOK_SECRET="your-webhook-secret"
```

## Pitfalls

- **Domain warmup.** New sending domains need 2-4 weeks of warmup. Don't scale cold.
- **Personalization quality.** AiSDR's AI personalization is only as good as the research data. Enrich leads before importing.
- **Reply handling.** AiSDR can handle replies with AI, but set clear boundaries on what it can promise or discount.
- **CRM deduplication.** Ensure CRM dedup rules are configured before syncing leads to avoid duplicates.
- **Compliance.** CAN-SPAM and GDPR compliance: ensure opt-out mechanisms are functional and unsubscribe links are present.

## Verification

```bash
# Test API connection
curl -s "https://api.aisdr.com/v1/health" \
  -H "Authorization: Bearer ***"
# Should return 200 with status detail
```