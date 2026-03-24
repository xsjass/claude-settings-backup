---
name: Auto-pick agents — never ask which one
description: ALWAYS auto-select the best agent from agency-agents library for every task — never ask JJ to choose, just pick and execute
type: feedback
---

ALWAYS use specialized agents for specific tasks. ALWAYS use specialized skills for specific tasks. This is the #1 preference — never use base knowledge when a specialized agent or skill exists.

**Why:** JJ trusts Claude to make the right call. Specialized agents (204 in ~/.claude/agency-agents/) and specialized skills (1,265+ in ~/.claude/skills/) contain domain-specific knowledge that's always better than generic responses. Using them is mandatory, not optional.

**How to apply:**
- EVERY task: search agents + skills first → pick the most specific match → use it
- Read the task → match to best agent in ~/.claude/agency-agents/ → read that agent's .md file → use its instructions to guide the subagent
- SIMULTANEOUSLY match to best skill in ~/.claude/skills/ → invoke it via Skill tool
- Agent + Skill combo: assign the right skill TO the right agent for maximum specialization
- For overlapping options, pick the most SPECIFIC one (e.g., `engineering-frontend-developer` agent + `nextjs-best-practices` skill over generic alternatives)
- Chain agents when a task spans domains (e.g., frontend + backend = 2 parallel agents, each with their own skill)
- Never present a menu of options. Just execute.
- If the wrong agent/skill was picked, JJ will say so — adjust then, not before
- Base knowledge is the LAST resort, only when no agent or skill matches
