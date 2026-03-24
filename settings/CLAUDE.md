# JJ Global Rules

## Mode
- Full autopilot. NEVER ask permission. Just execute.
- If blocked, find an alternative. If something fails, fix it.
- Loop until perfect.

## Communication
- Honest, direct, no sycophancy. Tell JJ when something is wrong.
- Short answers. Lead with action. No flattery.

## Workflow — ALWAYS USE THE FULL ARSENAL
- Every task: launch parallel subagents. Single-threaded = wrong.
- BEFORE writing any code, auto-search and load matching skills from ~/.claude/skills/ (1,267 available)
- BEFORE starting any task, auto-pick multiple if needed best agent personas from ~/.claude/agency-agents/ (179 available)
- Search ~/.claude/resources/public-apis.md for free APIs when needed

### Auto-Use These Tools On Every Task
- **RuFlo** (~/.claude/ruflo/): Agent orchestration platform — 134 specialized agent skills for swarm coordination, code review, architecture, testing, deployment. Use for complex multi-agent tasks.
- **Skills** (~/.claude/skills/): grep for keywords matching the task, read the skill, follow its patterns
- **Agency Agents** (~/.claude/agency-agents/): read the matching agent prompt, adopt its expertise
- **AST-Grep Rules** (~/.claude/ast-grep-essentials/): run on every code change to catch bugs/security issues
- **PR Agent** (~/.claude/ai-pr-reviewer/): use for any PR or code review
- **MiroFish** (~/.claude/MiroFish/): use for prediction/analysis tasks
- **Playwright** (~/.claude/playwright-cli/): use for any browser testing or scraping
- **n8n Workflows** (~/.claude/n8n-workflows/): use for automation tasks
- **Code Review Graph** (~/.claude/code-review-graph/): use for code quality analysis
- **System Prompts** (~/.claude/system-prompts/): reference for prompt engineering

### How To Auto-Pick
1. Take the task keywords (e.g. "frontend", "API", "security", "database")
2. `ls ~/.claude/skills/ | grep -i <keyword>` → read top matches
3. `ls ~/.claude/agency-agents/<category>/` → read the best agent prompt
4. Inject skill knowledge + agent persona into subagent prompts
5. Never work without a skill backing you up

## Quality
- Zero build errors before declaring "done"
- No hardcoded demo data, no security bypasses, no stubs
- Real content, not placeholders

## Stack
- Next.js 14+ (App Router), React 18+, TypeScript
- Tailwind CSS + Framer Motion
- Zustand (persisted state)
- Prisma + PostgreSQL
- Dark theme (#0a0a0f)

## Projects
1. Francify — French learning → C:/Users/xsjas/Desktop/Francify/
2. Phantom Trade AI — Day trading → E:/PROJECT 2 ( 2M )/
3. Project IGI — AI beat-making → E:/PROJECT IGI/
4. AI Arena — 3D battle game
5. Mathelo — Math learning
6. TCF Speaking Prep AI → C:/Users/xsjas/Desktop/TCF SPEAKING PREP AI/
