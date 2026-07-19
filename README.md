# Stack Insider AI Skills

[![skills.sh](https://skills.sh/badge.svg)](https://skills.sh/McClawdDigital/stack-insider-skills)

Agent skills for AI SaaS tools reviewed on **Stack Insider** (stack-insider.com). Each skill covers real agent workflows — orchestrating tools through their APIs, managing MCP connections, and chaining multi-tool processes.

## Included Skills

| Skill | Tool | Category | Install |
|-------|------|----------|---------|
| `lindy-agent` | Lindy AI Agent Platform | AI Agents | `npx skills add McClawdDigital/stack-insider-skills@lindy-agent` |
| `castmagic-content` | Castmagic Content Pipeline | Content | `npx skills add McClawdDigital/stack-insider-skills@castmagic-content` |
| `gamma-presentations` | Gamma AI Presentations | Creative | `npx skills add McClawdDigital/stack-insider-skills@gamma-presentations` |
| `aisdr-outreach` | AiSDR Sales Outreach | Sales | `npx skills add McClawdDigital/stack-insider-skills@aisdr-outreach` |
| `snowfire-content` | Snowfire AI Content Assembly | Content | `npx skills add McClawdDigital/stack-insider-skills@snowfire-content` |
| `reclaim-ai-scheduling` | Reclaim.ai Smart Scheduling | Productivity | `npx skills add McClawdDigital/stack-insider-skills@reclaim-ai-scheduling` |
| `tidio-customer-service` | Tidio AI Customer Service | Support | `npx skills add McClawdDigital/stack-insider-skills@tidio-customer-service` |

## Installation

```bash
# Install individual skills
npx skills add McClawdDigital/stack-insider-skills@lindy-agent
npx skills add McClawdDigital/stack-insider-skills@castmagic-content

# Or install the full package
npx skills add McClawdDigital/stack-insider-skills
```

## Structure

Each skill is a directory with a `SKILL.md` containing:
- **Frontmatter:** skill name, description, tags, metadata
- **Trigger Conditions:** when the agent should activate this skill
- **API Patterns:** authenticated curl commands for tool operations
- **Workflow Templates:** reusable multi-step processes
- **Environment Setup:** credentials, config variables
- **Pitfalls:** common failures and how to avoid them
- **Verification:** test command to confirm setup

## Full Reviews

For in-depth reviews and AI-readiness scores of these tools, visit [stack-insider.com](https://stack-insider.com/reviews).

## License

MIT — use, modify, and share freely.