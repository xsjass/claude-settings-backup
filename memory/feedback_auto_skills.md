---
name: Auto-select skills from library
description: ALWAYS proactively select and invoke relevant skills from ~/.claude/skills/ when working — never wait for JJ to type slash commands
type: feedback
---

Auto-select and invoke the best matching skill from the 1,264 skill library when working on tasks. Don't rely only on base knowledge when a specialized skill exists.

**Why:** JJ has 1,264 skills installed but they were never being used automatically. Skills contain specialized, opinionated knowledge that's better than generic responses.

**How to apply:**
- Before starting any significant task, mentally match it against known skill categories
- Invoke the skill via the Skill tool — don't just use base knowledge
- For overlapping skills, pick the most specific one (e.g., `nextjs-best-practices` over generic `frontend-developer`)
- jj- custom skills have NO special priority — treat ALL skills equally. Pick whichever is BEST for the task, custom or community.
- For TCF Speaking Prep AI project: ALWAYS physically search ~/.claude/skills/ directory (all 1,264 files) using grep/glob to find the best matching skill — read the skill file content, then invoke it. Prefer skills over base knowledge for EVERYTHING.
- When multiple skills apply to a complex task, chain them
- Scan the skill library before starting any task to find the best match
