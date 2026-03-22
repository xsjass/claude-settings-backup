---
name: Ralph Loop Pattern
description: Iterative agent loop pattern at ~/.claude/ralph-loop/ — externalize memory to files, one task per iteration, commit, repeat
type: reference
---

Cloned from github.com/abhishekbhakat/ralph-loop-for-antigravity (MIT license).

**Location:** `~/.claude/ralph-loop/`

**Pattern:** PRD.md (tasks) → progress.txt (tracking) → complete ONE task → append progress → commit → repeat until done.

**How to apply:** Use this iterative loop pattern for long autonomous tasks. Break work into PRD, track progress in a file, execute one task at a time with fresh context. Useful when tasks are too large for a single pass.
