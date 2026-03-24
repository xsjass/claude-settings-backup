---
name: Recording System Feedback
description: JJ wants mic/recording to feel instant like Duolingo/ELSA — study competitors and mimic their approach
type: feedback
---

Recording system must be fast and professional like competitor language apps (Duolingo, Babbel, ELSA Speak). JJ explicitly said to check other language websites and mimic their recording UX.

**Why:** Current system has ~4s delay on mic stop. Users shouldn't wait. Competitors feel instant.

**How to apply:**
- Always research competitor patterns before building voice/recording features
- Mic stop must feel instant (<100ms)
- Never block UI on transcription — show results progressively
- Use VAD for automatic speech detection instead of manual timers
- Parallel processing: don't wait for one step to complete before starting the next
