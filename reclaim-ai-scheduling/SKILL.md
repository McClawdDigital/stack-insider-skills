---
name: reclaim-ai-scheduling
description: "Protect focus time, optimize schedules, and manage calendar priorities with Reclaim.ai — AI-powered scheduling that learns your work patterns and defends your deep work blocks."
tags: [reclaim, scheduling, calendar, productivity, ai-scheduling, time-management]
---

# Reclaim.ai AI Scheduling

Manage calendar priorities and protect focus time with Reclaim.ai, orchestrated from Hermes. This skill covers focus block management, habit scheduling, meeting optimization, and task-to-calendar integration.

## Trigger Conditions

Use this skill when the user asks to:
- Block focus time or deep work on their calendar
- Schedule recurring habits (exercise, learning, admin)
- Optimize their meeting load and buffer times
- Set up task scheduling with automatic rescheduling
- Manage team availability and scheduling policies

## API Access

Reclaim.ai provides a REST API. Store your API key in Bitwarden:

```bash
bw get notes "Reclaim.ai API Key"
```

Base URL: `https://api.reclaim.ai/v1`

## Common Operations

### List Upcoming Events

```bash
curl -s "https://api.reclaim.ai/v1/events?status=scheduled&limit=10" \
  -H "Authorization: Bearer $RECLAIM_API_KEY" | jq '.'
```

### Create a Focus Block

```bash
curl -X POST "https://api.reclaim.ai/v1/events" \
  -H "Authorization: Bearer $RECLAIM_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "title": "Deep Work: Project Alpha",
    "duration_minutes": 120,
    "event_type": "focus_block",
    "priority": "high",
    "defend": true
  }'
```

### Create a Habit

```bash
curl -X POST "https://api.reclaim.ai/v1/habits" \
  -H "Authorization: Bearer $RECLAIM_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "title": "Morning Exercise",
    "duration_minutes": 45,
    "frequency": "daily",
    "preferred_time": "07:00",
    "minimum_duration": 30
  }'
```

### Get Scheduling Stats

```bash
curl -s "https://api.reclaim.ai/v1/stats" \
  -H "Authorization: Bearer $RECLAIM_API_KEY" | jq '.'
```

## Workflow Pattern

### Weekly Calendar Optimization

1. **Audit** — Check current scheduling stats (focus time %, meeting load)
2. **Block** — Create focus blocks for the week's priorities
3. **Habits** — Set up recurring habits with non-negotiable time slots
4. **Defend** — Enable AI defense on all focus blocks
5. **Review** — Check at end of week: what got pushed and why

## Environment Setup

```bash
export RECLAIM_API_KEY="your-api-key"
```

## Pitfalls

- **Over-scheduling.** Reclaim AI can be optimistic about available time. Set realistic duration estimates.
- **Calendar provider lock.** Reclaim only works with Google Calendar and Outlook. No iCloud support.
- **Defense mode.** High-priority blocks still get pushed by truly urgent events. Tag judiciously.
- **Habit accumulation.** Adding too many habits per day will result in none getting done. Start with 2-3 max.
- **Team scheduling.** Team features require higher-tier plans. Individual-first design.

## Verification

```bash
curl -s "https://api.reclaim.ai/v1/health" \
  -H "Authorization: Bearer $RECLAIM_API_KEY"
# Should return 200 with service status
```