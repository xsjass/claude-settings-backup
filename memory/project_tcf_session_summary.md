---
name: TCF Speaking Prep AI — Session Summary (2026-03-24)
description: Major session — mic fix, competitive upgrade, responsive overhaul, full audit with 66 bugs fixed to zero
type: project
---

## What was done (2026-03-24)

### Mic/Recording Overhaul
- Synchronous blob extraction (killed 4s delay → <100ms)
- Voice Activity Detection (@ricky0123/vad-web) for ~800ms silence detection
- Decoupled Whisper from critical path (runs in background for pronunciation)
- Streaming sentence TTS (AI speaks as it streams, not after)
- Fixed sentence detection bug (lastIndexOf was searching backwards)
- Fixed stopMediaRecorder dropping last ~100ms audio

### Competitive Upgrade (Tier 1)
- Dark mode: full CSS variable system, ThemeProvider, 22+ files refactored
- Gamification: XP, streaks, levels (Bronze→Diamond), daily goals, streak calendar
- Onboarding: 4-step wizard (language, CEFR level, daily goal, exam date)
- Pronunciation: word-level color-coded scores, audio comparison vs native
- Dashboard: XP bar, streak calendar, weekly chart, weakest area callout
- Settings: theme toggle, daily goal, exam date, speech speed, voice gender

### Responsive Overhaul
- Fixed overlapping controls in Learn and Mock Test pages
- Proper flex layout chains across all voice pages
- Responsive MicButton, MessageBubble, ChatWindow
- Sidebar capped at 75vw on mobile
- Safe area CSS for notched phones

### Full Audit (66 issues → 0)
- 3 CRITICAL security fixes (VIP JWT, access codes, cookie logout)
- 9 HIGH fixes (recording, backend persistence, XP awarding)
- 19 MEDIUM fixes (dark mode colors, WebSocket, Gemini roles)
- 22 LOW fixes (dead code, memory leaks, type safety)

**Why:** JJ wants the app to compete with Duolingo/ELSA/Babbel. Recording was too slow, no gamification, no dark mode, mobile was broken.

**How to apply:** TCF app is now at feature parity for Tier 1. Tier 2 (structured learning path, spaced repetition, session recording comparison) is next.
