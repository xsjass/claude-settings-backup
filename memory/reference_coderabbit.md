---
name: CodeRabbit Bug-Finding Rules
description: 184 AST-based bug/security rules at ~/.claude/ast-grep-essentials/ covering 15 languages — use for code auditing
type: reference
---

**AST-Grep Rules:** `~/.claude/ast-grep-essentials/rules/` — 184 rules for TypeScript, JavaScript, Python, HTML, Go, Rust, C++, Java, etc.
**AI PR Reviewer:** `~/.claude/ai-pr-reviewer/` — GitHub Action for AI code reviews.

**How to apply:** When auditing code or reviewing for bugs/security issues, reference these AST rules as patterns to check against. The rules catch: hardcoded secrets, insecure hashing, XSS, SQL injection, weak crypto, null checks, and more.
