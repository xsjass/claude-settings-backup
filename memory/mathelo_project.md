---
name: Mathelo Project — Complete State
description: Mathelo is a math-based execution library for AI agents. $10/mo subscription. Not open source. Full project state and architecture.
type: project
---

## What Mathelo IS
A math-based execution library/skill that AI agents use behind the scenes. NOT a user-facing tool. NOT open source. Paid subscription ($10/mo).

Human speaks English → AI understands → AI calls Mathelo → Mathelo COMPUTES (not predicts) → Human gets result. Mathelo is invisible to the human.

## Key Insight
Other AIs are DATA-based (predict from training). Mathelo is MATH-based (computes deterministically). 93% fewer tokens, 10-54,000x faster, 100% accurate, zero hallucination.

## Business Model
- Starter: $10/mo (1 key, 1 machine)
- Pro: $29/mo (5 keys, API, analytics)
- Enterprise: Custom
- License key system with expiration enforcement
- NOT open source. All rights reserved. Hide internals.

## Project Location
`C:\Users\xsjas\PROJECT 1M ( JJ )\mathelo\`

## Python Runtime
`C:\Users\xsjas\AppData\Local\Python\bin\python.exe` (Python 3.14.3)

## File Extension
`.mth` for Mathelo source files, `.mlc` for compiled bytecode

## Architecture (40+ files)

### Core Engine (`src/engine.py`)
- MatheloEngine class — the heart. Receives JSON instructions, computes results.
- 100+ opcodes for math, files, code execution, web, data, deploy
- License check on every execute() call
- English-to-instruction parser built in

### License System (`src/license.py`)
- HMAC-signed license keys: MTH-<hash>-<plan>-<expiry>-<signature>
- Checks on every engine call — no license = no execution
- Admin key generation: `mathelo generate-key email plan days`
- Stored at `~/.mathelo/license.key`

### Universal Transpiler (`src/universal_transpiler.py`)
- 17 input languages: Python, JS, Java, C#, Go, Rust, Ruby, PHP, Swift, Kotlin, Dart, Lua, Perl, R, Scala, Bash, C
- 14 output languages (same minus Perl, Scala, C)
- 238 total conversions
- Indentation-aware parsing for Python/Ruby
- Proper brace nesting for all C-style languages
- Uses `%placeholder%` templates (not `{placeholder}` — avoids Python format conflicts)

### Framework Generator (`src/frameworks.py`)
- 13 frameworks: React, Vue, Angular, Svelte, Next.js, Django, Flask, FastAPI, Express, Flutter, React Native, Electron, Static
- One config → complete project for any framework

### Web Framework (`src/web_framework.py`)
- Component-based HTML generation
- CSS presets (reset, typography, layout, components, nav, hero, footer, animations, dark)
- Landing page, dashboard, portfolio generators

### Hybrid AI Engine (PAUSED — built but not prioritized)
- `src/mathir.py` — Math IR: 30+ node types, type system, visitor pattern
- `src/frontend_python.py` — Python → Math IR via real AST parsing
- `src/codegen.py` — Math IR → Python, JS, Rust, Go, Java, C code generators
- `src/hybrid.py` — Hybrid engine tying frontend + IR + codegen
- `demo_hybrid.py` — Live demo (Python → 6 languages in 0.81ms)
- `benchmark_website_comparison.py` — Claude vs Claude+Mathelo website benchmark
- **Status:** Works but paused. IR doesn't compress enough for single conversions (8% savings). Multi-language is 85% savings but niche use case. Generated code lacks idiomatic quality vs Claude writing natively. JJ decided the original opcode engine is the real value, not the transpiler.
- **Decision:** Focus energy on the opcode engine (math, web gen, deterministic compute) — that's where real token savings are (82-93%).

### Other Modules
- `src/safety.py` — Sandboxed filesystem, blocked dangerous commands, rate limits
- `src/stdlib.py` — 20 stdlib modules (math, string, array, map, json, regex, crypto, time, stats, matrix, etc.)
- `src/ffi.py` — FFI bridge to 55 whitelisted Python modules (numpy, pandas, etc.), dangerous modules blocked
- `src/smart_evolution.py` — Brain v2: genetic programming, pattern learning, code synthesis, prediction
- `src/evolution.py` — Brain v1: pattern tracking, optimization
- `src/languages.py` — 345 opcodes mapped from ALL programming paradigms
- `src/async_engine.py` — Goroutines, channels, mutexes
- `src/pattern_match.py` — Rust/Haskell-style pattern matching
- `src/types.py` — Type system with inference
- `src/modules.py` — .mth file import system
- `src/transpiler.py` — Python/JS AST-based transpiler (older, detailed version)
- `src/ai_engine.py` — OpenAI, Anthropic, Stability AI, Ollama integration
- `src/tokens.py`, `src/lexer.py`, `src/parser.py`, `src/ast_nodes.py` — Original Mathelo language parser
- `src/interpreter.py`, `src/compiler.py`, `src/vm.py` — Original interpreter/compiler/VM

### CLI (`mathelo_mvp.py`)
Commands: ask, math, solve, convert, build, serve, repl, info, activate, deactivate, status, generate-key

### Website (`website/`)
- SDK-style landing page (NOT a playground for humans)
- Shows results, benchmarks, pricing — hides internals
- Pricing: $10/mo Starter, $29/mo Pro, Enterprise custom
- Benchmark results embedded: 93% fewer tokens, 54,527x faster

### Package (`mathelo/__init__.py`)
- `pip install mathelo` works (installed locally with `-e .`)
- Clean API: Engine, convert, get_agent_instructions, supported_languages
- `setup.py` for PyPI publishing

### AI Instructions (`AGENT_INSTRUCTIONS.md`)
- 6,097 char document that tells AI how to use Mathelo
- Opcode reference, examples, rules
- Embedded in AI system prompts via `get_agent_instructions()`

### Benchmark Results
- 8 tasks: fibonacci, prime, quadratic, stdev, determinant, code conversion, factorial, formula
- WITHOUT Mathelo: 857 tokens, 26.5s, 87.5% accuracy
- WITH Mathelo: 61 tokens, 0.486ms, 100% accuracy
- Website benchmark: 2,791 tokens vs 185 tokens (93% savings)
- At scale (1M req/day): saves $14.3M/year

### Installer
- `installer/dist/mathelo-setup.exe` (12MB Windows installer)
- `installer/dist/mathelo-0.2.0.zip` (portable package)
- `installer/setup.iss` (Inno Setup script)

## Creator
JJ — the user. All rights reserved.

**How to apply:** Always work inside `C:\Users\xsjas\PROJECT 1M ( JJ )\mathelo\`. Use Python at `C:\Users\xsjas\AppData\Local\Python\bin\python.exe`. Never expose internal opcodes/engine details publicly. Mathelo is a paid product.
