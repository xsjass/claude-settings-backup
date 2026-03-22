---
name: Use all tools aggressively when building
description: ALWAYS use skills, agents, MCPs, CLIs when building — prefer them over base knowledge, use as many parallel agents as needed
type: feedback
---

When building projects, ALWAYS:
1. Search and invoke relevant skills from ~/.claude/skills/ before writing code
2. Use specialized agents from ~/.claude/agency-agents/ with skill injection
3. Use MCP servers (Context7 for current docs, Playwright for testing, GitHub for repo mgmt)
4. Use CLIs (Vercel, Supabase) when applicable
5. Launch as many parallel agents as needed — no limit
6. Start from THINKING what is the best approach before coding
7. Save any useful approach/pattern to memory for future use

**Why:** JJ has 1,265+ skills, 204 agents, 3 MCPs, 5 CLIs — these exist to be used. Base knowledge is last resort.

**How to apply:** Before every task → search skills → pick best agent → inject skill → launch. Multiple agents in parallel for independent work. Always prefer specialized knowledge over generic.
