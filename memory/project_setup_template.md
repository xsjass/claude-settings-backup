---
name: Project Setup Template
description: Every new project should clone everything-claude-code repo for skills/config, and all work stays inside the project folder only
type: feedback
---

When the user says "create a new project", always:
1. Create the project folder as requested
2. Clone https://github.com/affaan-m/everything-claude-code.git inside it
3. Build inside that project folder using the skills from the repo

**Why:** User wants a consistent setup with 115+ skills (AI/agent engineering, backend/frontend patterns, testing, security, DevOps, etc.) available for every project. Repo has been security-scanned and verified SAFE.

**How to apply:**
- Clone the repo into every new project folder
- Use skills from `skills/` directory to guide work
- NEVER access files outside the user's project folder — stay within the project boundary only
