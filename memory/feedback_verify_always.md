---
name: Always verify builds and use max agents
description: After building, ALWAYS run build checks and fix errors. Use maximum parallel agents for every project. Save this for all projects.
type: feedback
---

After every build phase:
1. Run `npm run build` or equivalent to check for errors
2. Fix ALL errors before moving on
3. Verify every page/component compiles
4. Use as many parallel agents as possible for independent work

**Why:** JJ wants zero errors and maximum speed. Never declare "done" without verification.

**How to apply:** Every project, every phase — build check → fix → verify → next phase. Launch 3-5 agents for independent tasks. Never single-thread when parallel is possible.
