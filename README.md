# Crispy LinkedIn Agent Skills

Agent Skills and a plugin for [Crispy](https://crispy.sh). They let your AI agent work on your own LinkedIn account. Start with `crispy-linkedin` to connect your account and verify your session. Then route to the matching job skill for daily LinkedIn work.

The same folder installs in Claude Code, Codex, Gemini CLI, Copilot CLI, and any agent that reads Agent Skills. The Claude Code, Codex, and Gemini CLI installs include the skills and the hosted Crispy MCP server at https://crispy.sh/api/mcp. Copilot CLI installs the 7 skills and the plugin's `.mcp.json` file from the Claude Code plugin manifest. The Agent Skills install adds the skills only. The `crispy-linkedin` skill then connects your agent to the MCP server.

## Install

### Claude Code

Install the plugin from inside Claude Code:

```text
/plugin install crispy-linkedin --marketplace shyftai/crispy-linkedin
```

Or from your terminal:

```bash
claude plugin install crispy-linkedin --marketplace shyftai/crispy-linkedin
```

Then run `/mcp` inside Claude Code and sign in to Crispy in your browser.

### Codex

```bash
codex plugin marketplace add shyftai/crispy-linkedin
codex plugin add crispy-linkedin@crispy-linkedin
```

Then run `codex mcp login crispy` and sign in to Crispy in your browser.

### Gemini CLI

```bash
gemini extensions install https://github.com/shyftai/crispy-linkedin
```

Then run `/mcp auth crispy` inside Gemini CLI and sign in to Crispy in your browser.

### Copilot CLI

```bash
copilot plugin marketplace add shyftai/crispy-linkedin
copilot plugin install crispy-linkedin@crispy-linkedin
```

Copilot CLI reads the Claude Code plugin manifest. It installs the 7 skills and the plugin's `.mcp.json` file.

### Any Agent Skills harness

Install the skills only:

```bash
npx skills add shyftai/crispy-linkedin
```

Then follow the `crispy-linkedin` skill. It connects your agent to the Crispy MCP server.

### Test a local checkout

Clone the repository and load the folder directly:

```bash
git clone https://github.com/shyftai/crispy-linkedin
cd crispy-linkedin
claude --plugin-dir .
```

For Gemini CLI, run `gemini extensions link .` from the same folder.

## Example Prompts

- "Check my LinkedIn inbox and list the conversations that need a reply."
- "Find heads of sales at fintech companies in Berlin and save them to a list."
- "Draft a LinkedIn post about our product launch in my writing style. Show it to me before you publish."
- "Summarize how my LinkedIn posts performed over the last 30 days."

## Data and Actions

The skills call Crispy's MCP server at https://crispy.sh/api/mcp. You sign in with OAuth in your browser. You can also use a Crispy API key that you create at https://crispy.sh/dashboard/api-keys and set as `CRISPY_API_KEY` in your own environment. The skills never ask for your key in chat and never write the key itself into a file.

Crispy runs every action on the LinkedIn account you connected at https://crispy.sh/dashboard. Write actions act as you, on your own account. Other people see them as coming from you.

Read tools look things up and do not post or send anything. Examples are `search_people`, `get_profile`, `list_conversations`, and `get_account`. A profile lookup does not notify the person unless you ask for it.

These tool classes write to LinkedIn:

| Class | What it does | Example tools |
|---|---|---|
| Messages | Send, forward, edit, schedule, and delete messages, InMail, and voice notes | `send_message`, `send_inmail`, `send_voice_message`, `schedule_message`, `delete_message`, `delete_chat` |
| Invitations and network | Send, withdraw, and answer invitations, follow and unfollow, endorse, and remove connections | `send_invitation`, `cancel_invitation`, `respond_to_invitation`, `follow_user`, `endorse_skills`, `remove_connection` |
| Posts and comments | Publish, schedule, repost, react, comment, reply, and delete | `create_post`, `publish_draft`, `repost_post`, `react_to_post`, `comment_on_post`, `reply_to_comment`, `delete_post` |
| Campaigns | Create, launch, pause, and delete multi-step outreach campaigns | `upsert_campaign`, `confirm_campaign_launch`, `manage_outreach`, `delete_campaign` |
| Profile | Edit your own LinkedIn profile | `edit_my_profile` |

Other write tools change only your data inside Crispy, such as lists, contacts, tags, notes, drafts, labels, saved searches, and settings. They do not post to LinkedIn.

How the skills handle writes:

- The agent shows you the exact text and recipient before any write runs. It waits for your approval.
- One approval covers only the items shown.
- Campaigns always run a launch preview first. Nothing sends until you confirm.
- The agent warns you before permanent actions such as deleting a post or removing a connection.
- Crispy enforces daily limits on your account. You manage them at https://crispy.sh/dashboard/security.

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

## Support

Email support@crispy.sh or visit https://crispy.sh/contact.
