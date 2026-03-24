---
name: Claude-Mem Plugin
description: Persistent memory plugin for Claude Code - install in every future project. Located at C:/Users/xsjas/claude-mem-main/claude-mem-main/
type: reference
---

Claude-mem is a persistent memory compression system for Claude Code. Installed as a plugin.

**Source:** C:\Users\xsjas\claude-mem-main\claude-mem-main\
**Installed to:** ~/.claude/plugins/marketplaces/thedotmack/

**Install steps for new projects:**
1. cd to claude-mem-main folder
2. npm install
3. cp -r plugin/* ~/.claude/plugins/marketplaces/thedotmack/

**How to apply:** Install this plugin in every new project for persistent memory across sessions. The plugin provides SessionStart, PostToolUse, and Summary hooks that capture and compress context.
