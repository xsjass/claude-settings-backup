---
name: Auto-pick agents — never ask which one
description: ALWAYS auto-select the best agent from agency-agents library for every task — never ask JJ to choose, just pick and execute
type: feedback
---

Never ask JJ which agent to use. Auto-pick the best one based on the task.

**Why:** JJ trusts Claude to make the right call. Asking "which agent do you want?" wastes time. Claude knows the 204 agents and 1,264 skills — match them to the task and go.

**How to apply:**
- Read the task → match to best agent in ~/.claude/agency-agents/ → read that agent's .md file → use its instructions to guide the subagent
- For overlapping agents, pick the most specific one
- Chain agents when a task spans domains (e.g., frontend + backend = 2 parallel agents)
- Never present a menu of options. Just execute.
- If the wrong agent was picked, JJ will say so — adjust then, not before
