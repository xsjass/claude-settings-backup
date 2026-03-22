---
name: jj-self-learn
description: Self-learning loop — on failure, analyze why, pivot to a totally different approach, test it, and loop until success. Never retry the same failing approach twice.
risk: safe
source: custom
date_added: "2026-03-22"
---

# Self-Learn Loop

Autonomous failure-driven learning loop. Every failure triggers a NEW approach, not a retry.

## Core Rule
**NEVER retry the same approach twice.** Every failure MUST produce a fundamentally different strategy.

## Loop Protocol

```
ATTEMPT_LOG = []
MAX_APPROACHES = 5
current_approach = 1

WHILE task NOT solved AND current_approach <= MAX_APPROACHES:

  1. PLAN — Design approach for this attempt
     - If attempt > 1, review ALL previous failures
     - New approach MUST differ fundamentally from all logged approaches
     - State clearly: "Approach {N}: {strategy}" and WHY it differs

  2. EXECUTE — Implement the approach
     - Write code / make changes
     - Keep changes isolated so they can be rolled back

  3. TEST — Verify it works
     - Run build, tests, or manual verification
     - Capture the EXACT error output if it fails

  4. EVALUATE — Did it work?

     IF SUCCESS:
       → Log: "✅ Approach {N} SUCCEEDED: {strategy}"
       → Enter REFINEMENT LOOP (see below)
       → DONE

     IF FAIL:
       → Log: "❌ Approach {N} FAILED: {strategy} — Reason: {root_cause}"
       → Add to ATTEMPT_LOG with full context
       → Rollback changes from this approach
       → ANALYZE the failure:
         - What SPECIFICALLY went wrong?
         - What assumption was incorrect?
         - What category of solution is now eliminated?
       → PIVOT: Design next approach from a DIFFERENT angle
         - Different library? Different algorithm? Different architecture?
         - If approaches 1-2 were incremental fixes, approach 3+ must be radical
       → current_approach += 1
       → CONTINUE

  IF all 5 approaches exhausted:
    → Present ATTEMPT_LOG to user
    → Ask: "5 approaches failed. Here's what I tried and why each failed. Want me to try 5 more, or should we rethink the goal?"
```

## Refinement Loop (After Success)

```
WHILE refinement_needed:
  1. Review working solution for:
     - Edge cases not covered
     - Performance issues
     - Code quality / clean code
     - Security concerns
  2. Apply improvements incrementally
  3. Test after each improvement
  4. If improvement breaks something → revert that improvement only
  5. Stop when solution is solid
```

## Pivot Strategy Matrix

When an approach fails, pick from a DIFFERENT category:

| Attempt | Strategy Category |
|---|---|
| 1 | **Direct** — Most obvious solution |
| 2 | **Alternative library/tool** — Same goal, different means |
| 3 | **Architectural pivot** — Restructure the approach entirely |
| 4 | **Simplify** — Strip to bare minimum, build up |
| 5 | **Unconventional** — Creative/hacky solution that just works |

## Attempt Log Format

Maintain a running log during execution:

```
## Self-Learn Attempt Log
Task: {description}

### Approach 1: {name}
Strategy: {what}
Result: ❌ FAILED
Root Cause: {why}
Eliminated: {what category of solutions this rules out}

### Approach 2: {name}
Strategy: {what — must differ from approach 1}
Result: ❌ FAILED
Root Cause: {why}
Eliminated: {what this rules out}

### Approach 3: {name}
Strategy: {what — radical pivot}
Result: ✅ SUCCESS
Refinements applied: {list}
```

## Rules

1. **No same approach twice** — If you used `fetch`, try `axios`. If you used REST, try GraphQL. If you used a loop, try recursion. DIFFERENT.
2. **Rollback on fail** — Don't accumulate broken code. Clean slate for each approach.
3. **Log everything** — Every attempt, every error, every reason. This IS the learning.
4. **Escalate pivot intensity** — Approach 1-2 can be similar-ish. Approach 3+ must be radical.
5. **Refinement after success** — Finding something that works is step 1. Making it production-quality is step 2.
6. **Use agents for parallel exploration** — When stuck, launch 2-3 agents trying different approaches simultaneously.
7. **Search skills library** — Before each new approach, grep ~/.claude/skills/ for relevant skills that might inform the strategy.
