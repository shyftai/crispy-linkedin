# Crispy LinkedIn Agent Skills

Public Agent Skills and Claude Code plugin for [Crispy](https://crispy.sh). Start with `crispy-linkedin` to connect your LinkedIn account and verify your session. Then route to the matching job skill for daily LinkedIn work.

## Install

### Claude Code Plugin (Skills and MCP Server)

Install the plugin in Claude Code:

```text
/plugin install crispy-linkedin --marketplace shyftai/crispy-linkedin
```

Or test from a local checkout:

```bash
claude --plugin-dir ./agent-skills
```

### Agent Skills CLI

Install the skills into any compatible agent harness:

```bash
npx skills add shyftai/crispy-linkedin
```

## Included Skills

| Skill | Job |
|---|---|
| `crispy-linkedin` | Onboarding, fit check, OAuth or `CRISPY_API_KEY` setup, session verification, first read-only result, and routing |
| `linkedin-prospecting` | Find people, companies, and posts, enrich profiles, research competitors, and qualify leads into lists |
| `linkedin-outreach` | Triage the inbox, reply in your writing style, send invitations, and launch previewed outreach campaigns |
| `linkedin-content` | Load your writing style, draft and publish posts, engage with niche discussions, and reply to comments |
| `linkedin-intelligence` | Track post, profile, network, and campaign performance, view profile visitors, and build weekly reports |
| `linkedin-sales-navigator` | Run deep people and company searches with Sales Navigator filters, manage saved searches, and save leads |
| `linkedin-playbooks` | Execute end-to-end reviewed workflows from Crispy playbooks and recipes, including CRM sync |

## Live Sources

- Recipes (machine-readable): https://crispy.sh/recipes.md
- Recipes hub: https://crispy.sh/recipes
- Playbooks hub: https://crispy.sh/playbooks
- Tool catalog and schemas: https://crispy.sh/llms.txt and https://crispy.sh/llms-full.txt
- Documentation: https://crispy.sh/docs
- Privacy: [Privacy Policy](https://crispy.sh/privacy)
- Terms: [Terms of Service](https://crispy.sh/terms)
