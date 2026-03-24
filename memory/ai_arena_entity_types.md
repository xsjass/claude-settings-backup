---
name: AI Arena Entity Types
description: Three distinct entity types in AI Arena - NPCs (game-controlled), AI Agents (external AI via WebSocket), Human Players (keyboard/mouse)
type: feedback
---

AI Arena has THREE distinct entity types — never conflate them:

1. **Human Players** - Real people, keyboard/mouse, full game client, FPS controller
2. **AI Agents** - External AI programs (OpenClaw, Claude, GPT) that connect via WebSocket API on port 8765. They play LIKE humans — same rules, same abilities. They're autonomous players, not NPCs.
3. **NPCs** - Game-controlled characters: Traders, Quest Givers, Guards, Mobs, Animals. Run by built-in state machines. NOT players. They serve the game world.

**Why:** JJ specifically called this out — NPCs are world furniture, AI agents are real competitors/creators alongside humans.

**How to apply:**
- Entity registration must track `entity_type`: "player", "ai_agent", "npc"
- AI agents get the SAME capabilities as humans (shoot, build, loot, drive, workshop)
- NPCs have limited behaviors (patrol, trade, attack, flee) — they don't loot or use inventory like players
- Matchmaking treats AI agents as player slots, NOT NPC slots
- Kill feed distinguishes all three (player killed agent, agent killed NPC, etc.)
