---
name: tidio-customer-service
description: "Deploy AI-powered customer service agents with Tidio — set up chatbots, automate ticket management, configure live chat, and integrate with e-commerce platforms."
tags: [tidio, customer-service, chatbot, live-chat, ecommerce, support-automation, ai-chat]
---

# Tidio Customer Service Automation

Deploy and manage AI customer service chatbots with Tidio, orchestrated from Hermes. This skill covers chatbot setup, automation rules, live chat management, ticket workflows, and e-commerce integration.

## Trigger Conditions

Use this skill when the user asks to:
- Set up an AI chatbot for customer support
- Configure automated responses and triggers
- Manage live chat agents and routing
- Integrate Tidio with e-commerce platforms (Shopify, WooCommerce)
- Review chat analytics and customer satisfaction data

## API Access

Tidio provides a REST API. Store your API key in Bitwarden:

```bash
bw get notes "Tidio API Key"
```

Base URL: `https://api.tidio.com/v1`

## Common Operations

### List Conversations

```bash
curl -s "https://api.tidio.com/v1/conversations?status=open&limit=20" \
  -H "Authorization: Bearer $TIDIO_API_KEY" | jq '.'
```

### Create Automation Rule

```bash
curl -X POST "https://api.tidio.com/v1/automation-rules" \
  -H "Authorization: Bearer $TIDIO_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Order Status Inquiry",
    "trigger": {
      "type": "keyword",
      "keywords": ["where is my order", "order status", "tracking"]
    },
    "response": {
      "type": "ai_reply",
      "template": "I can help you track your order. Could you please provide your order number?",
      "fallback": "agent"
    },
    "channels": ["live_chat", "email"]
  }'
```

### Set Agent Routing

```bash
curl -X POST "https://api.tidio.com/v1/routing-rules" \
  -H "Authorization: Bearer $TIDIO_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "VIP Customer Routing",
    "conditions": [
      {"field": "customer_lifetime_value", "operator": "gt", "value": 1000}
    ],
    "action": "assign_to_team",
    "team_id": "team_vip"
  }'
```

### Get Chat Analytics

```bash
curl -s "https://api.tidio.com/v1/analytics/summary?period=7d" \
  -H "Authorization: Bearer $TIDIO_API_KEY" | jq '.metrics'
```

## Workflow Pattern

### Chatbot Deployment

1. **Identify intents** — List top 5-10 customer questions
2. **Create automations** — Build keyword-triggered AI responses
3. **Set fallback rules** — Define when an agent takes over
4. **Configure routing** — Assign conversations to right teams
5. **Test** — Run test conversations across channels
6. **Deploy** — Go live and monitor first 48 hours

## Environment Setup

```bash
export TIDIO_API_KEY="your-api-key"
```

## Pitfalls

- **Keyword overlap.** Multiple automation rules can trigger on the same message. Order rules by priority.
- **AI accuracy.** Tidio's AI handles English well but may struggle with non-English or mixed-language queries.
- **Escalation latency.** The handoff between AI and human agent can feel slow. Set expectations in the AI response.
- **Reporting gaps.** Advanced CSAT tracking requires Shopify/enterprise plans. Basic plans have limited analytics.
- **Mobile agent app.** The mobile agent app is functional but lacks full desktop capabilities.

## Verification

```bash
curl -s "https://api.tidio.com/v1/health" \
  -H "Authorization: Bearer $TIDIO_API_KEY"
# Should return 200
```