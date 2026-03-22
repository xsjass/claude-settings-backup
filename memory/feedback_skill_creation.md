---
name: Skill creation rules
description: When creating skills — always name them with jj- prefix, use dedicated agent with specific skills, save to memory automatically
type: feedback
---

When JJ says "make this a skill" or "create a skill":

1. **Always prefix with `jj-`** — e.g., `jj-security-audit`, `jj-self-learn`
2. **Each skill must assign a specific agent** with specific sub-skills from the 1,264 library
3. **Save to `~/.claude/skills/jj-{name}/skill.md`** immediately
4. **Update global CLAUDE.md** with the new skill in the custom skills list
5. **Save a memory reference** so future conversations know it exists
6. **Never ask for the name** — auto-pick a clear, descriptive name

**Why:** JJ wants custom skills to be first-class, properly named, agent-backed, and persistent. Every skill JJ creates is important enough to track globally.

**How to apply:** On any "make a skill" or "save this as a skill" request — name it, write it, register it in CLAUDE.md, save memory. One shot, no questions.
