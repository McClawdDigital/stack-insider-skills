---
name: lindy-agent
description: "Orchestrate Lindy AI agents from Hermes — trigger workflows, manage agent configurations, and chain Lindy automations as part of larger AI-driven processes."
tags: [lindy, ai-agents, automation, workflow-orchestration, task-chaining]
category: autonomous-ai-agents
created: 2026-07-19
---

# Lindy Agent

Orchestrate Lindy AI agents from Hermes. This skill covers triggering Lindy workflows, managing agent configurations, and integrating Lindy automations into larger multi-agent processes.

## Trigger Conditions

Use this skill when the user asks to:
- Trigger a Lindy agent or workflow from Hermes
- Configure or update Lindy agent settings
- Build a multi-step process that includes Lindy agents
- Integrate Lindy with other tools via Hermes

## API Access

Lindy provides a REST API. Your Lindy workspace API key should be stored in Bitwarden:

```bash
# Retrieve Lindy API key
bw get notes "Lindy API Key"
```

Base URL: `https://api.lindy.ai/v1`

## Common Operations

### Trigger a Lindy Workflow

```bash
curl -X POST "https://api.lindy.ai/v1/workflows/{workflow_id}/trigger" \
  -H "Authorization: Bearer $LINDY_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "input": {
      "data": "<payload>"
    }
  }'
```

### List Available Agents

```bash
curl -s "https://api.lindy.ai/v1/agents" \
  -H "Authorization: Bearer $LINDY_API_KEY" | jq '.'
```

### Get Agent Status

```bash
curl -s "https://api.lindy.ai/v1/agents/{agent_id}/status" \
  -H "Authorization: Bearer $LINDY_API_KEY" | jq '.'
```

## Workflow Patterns

### Lindy as a Processing Step

When Lindy is one step in a larger Hermes-orchestrated pipeline:

1. Prepare input data (from prior automation steps)
2. POST to Lindy workflow trigger
3. Poll for completion using the returned run ID
4. Pass Lindy output to the next tool in the chain

### Chaining Multiple Lindy Agents

For complex processes that span multiple Lindy agents:

1. Agent A processes input → produces intermediate result
2. Pass Agent A's output as Agent B's input
3. Collect final result from the last agent in the chain

## Environment Setup

```bash
export LINDY_API_KEY="your-api-key-here"
export LINDY_WORKSPACE_ID="your-workspace-id"
```

## Pitfalls

- **Rate limits:** Lindy workflows have per-minute rate limits. Use delays between triggers for batch operations.
- **Webhook responses:** Lindy can POST results to a webhook — configure this for async workflows instead of polling.
- **Agent names vs IDs:** Always use agent IDs (UUIDs) in API calls, not display names.
- **Payload size:** Lindy has a ~1MB payload limit per workflow trigger. Split large payloads across multiple triggers.

## Verification

After setting up integration:

```bash
# Test API connectivity
curl -s "https://api.lindy.ai/v1/agents" \
  -H "Authorization: Bearer $LINDY_API_KEY" | jq '. | length'
# Should return a count of available agents
```