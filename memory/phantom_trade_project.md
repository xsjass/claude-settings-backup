---
name: Phantom Trade AI Project
description: AI day trading platform - PROJECT 2 at E:/PROJECT 2 ( 2M )/ - crypto+stocks, hacker UI, 10 AI engines, 7 brokers
type: project
---

Phantom Trade AI — autonomous AI day trading platform.

Location: E:/PROJECT 2 ( 2M )/
- Frontend: Next.js on port 5777 (standalone build)
- Backend: FastAPI/Python on port 8200

User is in Canada — Alpaca doesn't work there. Use Coinbase, Binance, or Kraken.

AI Keys (user's own, free tier):
- Groq: configured in .env (free, 30 req/min)
- Gemini: configured in .env (free, 15 req/min)
- Scan interval: 30 seconds to stay in free tier

10 Engines built: 6-Agent Swarm, Emotion Engine, Darwin Evolution, Deja Vu, Cascade Mapper, Portfolio Immune System, Pattern Detector, Technical Analysis, Risk Manager, Social Intelligence

7 Brokers supported: Coinbase, Binance, Kraken, KuCoin, Bybit, Interactive Brokers, Alpaca

Known issues:
- RSI shows 100 on all assets (not enough price history, needs more scan cycles)
- 0 trading signals generated (same reason — needs history)
- Coinbase key auth not tested yet (user needs to provide correct key_name format)
- Frontend hacker theme CSS confirmed working with standalone build

**Why:** User wants to launch this platform and make money from subscriptions. Risky short-term trading with disclaimers.

**How to apply:** Keep building autonomously. Don't ask permission. Focus on making it launchable.
