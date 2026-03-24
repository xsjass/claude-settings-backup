---
name: jj-security-audit
description: Deep security audit of any repo, package, or code before installing or using it. Always run this before adding anything external to the system.
risk: safe
source: custom
date_added: "2026-03-22"
---

# Security Audit Skill

MANDATORY: Run this audit on ANY external code, repo, package, or dependency before installing or keeping it.

## Trigger
- Before cloning any GitHub repo
- Before installing any npm/pip/cargo package
- Before using any external API
- Before running any downloaded script
- When user says "check if safe", "is this legit", "audit this"

## Audit Protocol

Launch a dedicated **security-audit agent** with the following instructions:

```
AGENT TYPE: security-auditor
SKILL REFERENCES: /security-auditor, /find-bugs, /vulnerability-scanner
CODERABBIT RULES: ~/.claude/ast-grep-essentials/rules/
```

### Step 1: Repo Verification
- Stars, forks, license, last update, archived status
- Owner reputation (org vs random user)
- Open security advisories
- Is it a fork of something legit?

### Step 2: Code Scan — Read EVERY file
Check ALL source files for:

**Python:**
- `eval()`, `exec()`, `__import__()`, `compile()`
- `subprocess`, `os.system`, `os.popen`
- `base64.b64decode` hiding payloads
- `socket`, `requests` to hardcoded IPs/domains
- `keylogger`, `screenshot`, `clipboard` access
- Obfuscated variable names or encoded strings

**JavaScript/TypeScript:**
- `eval()`, `Function()`, `new Function()`
- `document.cookie`, `localStorage` exfiltration
- `crypto` mining patterns
- `fetch`/`XMLHttpRequest` to unknown endpoints
- `postinstall`, `preinstall` scripts in package.json

**General:**
- Hidden files/directories that shouldn't exist
- Binary executables disguised as other file types
- Encoded/encrypted blobs
- Network calls to hardcoded IPs
- File access outside project directory
- Credential harvesting patterns
- Reverse shells or C2 callbacks

### Step 3: Config Audit
- `docker-compose.yml` — suspicious volume mounts (`/`, `/etc/`, `~/.ssh/`)
- `.env` files with real credentials
- CI/CD configs with suspicious steps
- Package manifests with lifecycle hooks

### Step 4: Dependency Check
- Known vulnerable packages
- Typosquatted package names
- Packages with low download counts + high permissions

## Output Format

```
## SECURITY AUDIT: {repo/package name}

### VERDICT: ✅ CLEAN / ⚠️ SUSPICIOUS / ❌ MALICIOUS

| Check | Result |
|---|---|
| eval/exec | ✅/❌ |
| Hardcoded IPs | ✅/❌ |
| Credential harvesting | ✅/❌ |
| Obfuscated code | ✅/❌ |
| Suspicious binaries | ✅/❌ |
| Lifecycle scripts | ✅/❌ |
| Known vulnerabilities | ✅/❌ |

### Details
{specific findings with file paths and line numbers}

### Recommendation
SAFE TO USE / DELETE IMMEDIATELY / USE WITH CAUTION
```

## Rules
1. **Be paranoid** — assume everything is malicious until proven clean
2. **Read EVERY file** — don't skip anything, malware hides in unlikely places
3. **Check binaries** — any executable or compiled file is suspicious
4. **Verify domains** — any hardcoded URL/IP must be explained
5. **If in doubt, flag it** — false positives are better than missed malware
6. **Auto-delete if malicious** — don't wait for user confirmation on clear threats
7. **Always report** — even if clean, show the full audit table
