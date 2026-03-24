---
name: jj-agent-with-skill
description: Launch agents pre-loaded with specific skill knowledge. Read the skill file, inject its instructions into the agent prompt, so the agent operates WITH that skill's expertise.
risk: safe
source: custom
date_added: "2026-03-22"
---

# Agent + Skill Injection

Agents can't call the Skill tool directly. Instead, INJECT skill knowledge into the agent's prompt.

## Protocol

```
1. IDENTIFY the task
2. SEARCH ~/.claude/skills/ for the best matching skill
3. READ the skill's skill.md file content
4. SEARCH ~/.claude/agency-agents/ for the best matching agent
5. READ the agent's .md file content
6. LAUNCH the Agent tool with a prompt that includes:
   - The agent persona (from agency-agents)
   - The skill instructions (from skills/)
   - The actual task
```

## Prompt Template

When launching an agent, structure the prompt like this:

```
You are a {agent_role} with the following expertise:

--- AGENT PERSONA ---
{paste content from ~/.claude/agency-agents/{agent}.md}

--- SKILL KNOWLEDGE ---
{paste content from ~/.claude/skills/{skill}/skill.md}

--- TASK ---
{the actual task to complete}

--- RULES ---
- Follow the skill instructions precisely
- Use the agent persona for decision-making style
- Output production-quality work
```

## Examples

### Frontend task:
- Agent: `engineering-frontend-developer.md`
- Skill: `nextjs-best-practices/skill.md` + `tailwind-patterns/skill.md`
- Task: "Build the speaking practice page"

### Security audit:
- Agent: `engineering-security-engineer.md`
- Skill: `security-auditor/skill.md` + CodeRabbit rules reference
- Task: "Audit this repo for vulnerabilities"

### Code review:
- Agent: `engineering-code-reviewer.md`
- Skill: `code-reviewer/skill.md`
- Task: "Review these files for quality"

## Rules
1. ALWAYS read skill + agent files before launching — don't guess their content
2. For large skills, extract the KEY rules only (keep agent prompt under 4000 words)
3. Multiple skills can be injected into one agent if they're complementary
4. The agent persona sets the STYLE, the skill sets the KNOWLEDGE
5. If no matching agent exists, use skill-only injection
6. If no matching skill exists, use agent-only injection
