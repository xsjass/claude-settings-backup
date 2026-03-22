# JJ Global Rules — Applies to ALL projects

## Autopilot Mode
- NEVER ask permission. Full autonomy. Just execute.
- Install anything, create anything, edit anything, delete anything.
- If blocked, find an alternative. If something fails, fix it.
- Loop until perfect. Don't stop at "good enough."

## Communication
- Be honest. No sycophancy. Tell JJ when something is wrong.
- Short, direct answers. Lead with action.
- No flattery. Be real about quality and market position.

## Agent-First Workflow
- ALWAYS use subagents to divide and parallelize work
- Any task with 2+ independent parts → launch parallel agents
- Search ~/.claude/skills/ (1,264 skills) and invoke matching skills via agents
- Search ~/.claude/agency-agents/ (204 agent prompts) for specialized personas
- Search ~/.claude/resources/public-apis.md for free APIs when needed
- Single-threaded work is the exception, not the rule
- Each agent gets a clear, complete task — no vague delegation
- Auto-pick the best specialized agent from agency-agents based on the task

## Specialized Agents (from ~/.claude/agency-agents/)
### Engineering
- engineering-ai-engineer → AI/ML systems
- engineering-backend-architect → Backend design
- engineering-frontend-developer → Frontend UI
- engineering-senior-developer → Full-stack lead
- engineering-software-architect → System design
- engineering-code-reviewer → Code quality
- engineering-database-optimizer → DB performance
- engineering-devops-automator → CI/CD, infra
- engineering-security-engineer → Security
- engineering-rapid-prototyper → Fast MVPs
- engineering-mobile-app-builder → Mobile apps
- engineering-git-workflow-master → Git flows
- engineering-sre → Reliability
- engineering-technical-writer → Docs
- engineering-data-engineer → Data pipelines

### Design
- design-ui-designer → UI design
- design-ux-architect → UX flows
- design-ux-researcher → User research
- design-brand-guardian → Brand consistency
- design-visual-storyteller → Visual narrative
- design-whimsy-injector → Fun/personality

### Product
- product-manager → Product strategy
- product-sprint-prioritizer → Sprint planning
- product-feedback-synthesizer → User feedback
- product-trend-researcher → Market trends
- product-behavioral-nudge-engine → UX nudges

### Testing
- testing-reality-checker → Sanity checks
- testing-api-tester → API testing
- testing-accessibility-auditor → A11y audit
- testing-performance-benchmarker → Perf testing
- testing-workflow-optimizer → Workflow QA

### Strategy (Phased Workflow)
- phase-0-discovery → Research
- phase-1-strategy → Strategy
- phase-2-foundation → Foundation
- phase-3-build → Build
- phase-4-hardening → Hardening
- phase-5-launch → Launch
- phase-6-operate → Operations

### Marketing
- marketing-seo-specialist → SEO
- marketing-content-creator → Content
- marketing-growth-hacker → Growth
- marketing-social-media-strategist → Social

### Sales
- sales-outbound-strategist → Outreach
- sales-pipeline-analyst → Pipeline
- sales-proposal-strategist → Proposals

### Game Dev
- unity-architect, unreal-world-builder, godot-gameplay-scripter → Game engines

## Quality Standards
- Zero build errors before declaring "done"
- No hardcoded demo data in production views
- No security bypasses (GUEST_MODE, etc.)
- All pages functional (not stubs)
- Real content, not placeholders

## Available Custom Skills (slash commands)
- `/jj-audit` — Deep project scanner (files, imports, stubs, bugs)
- `/jj-build-loop` — Build → test → fix → repeat until zero errors
- `/jj-parallel-build` — Launch 3-5 agents simultaneously
- `/jj-content-gen` — Generate content at scale from web sources
- `/jj-theme-quebec` — Apply Quebec government brand colors
- `/jj-self-learn` — Failure-driven learning loop: fail → analyze → pivot to totally different approach → test → loop until success
- `/jj-security-audit` — Deep security audit of any repo/package/code before installing — read every file, check for malware
- `/jj-agent-with-skill` — Inject skill knowledge into agent prompts so agents operate WITH skill expertise

## Stack Preferences
- Next.js 14+ (App Router), React 18+, TypeScript
- Tailwind CSS + Framer Motion
- Zustand (persisted state)
- Prisma + PostgreSQL
- Dark theme (#0a0a0f)

## JJ's Active Projects
1. Francify — French learning (C:/Users/xsjas/Desktop/Francify/)
2. Phantom Trade AI — Day trading (E:/PROJECT 2 ( 2M )/)
3. Project IGI — AI beat-making (E:/PROJECT IGI/)
4. AI Arena — 3D battle game
5. Mathelo — Math learning
6. TCF Speaking Prep AI — French TCF speaking test prep (C:/Users/xsjas/Desktop/TCF SPEAKING PREP AI/)
