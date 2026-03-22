---
name: TCF Speaking Prep AI Project
description: AI-powered TCF Canada speaking exam prep — live voice AI, 3 modes, $49.99/mo, Clerk auth, Groq+Gemini, Vercel deployed
type: project
---

**Location:** `C:/Users/xsjas/Desktop/tcf-prep/`
**GitHub:** https://github.com/xsjass/tcf-speaking-prep-ai (private)
**Live:** https://tcf-prep.vercel.app
**Settings backup:** https://github.com/xsjass/claude-settings-backup

## Tech Stack
- Next.js 15 + TypeScript + Tailwind CSS + Framer Motion
- Clerk Auth (Google + email) + VIP access codes (JASS1130, SONA0329)
- Stripe $49.99/month subscription
- Groq (Llama 3.3 70B) + Google Gemini (free, auto-fallback)
- Edge TTS + Google Translate TTS + Browser SpeechSynthesis (all free)
- Web Speech API for STT (free, unlimited)
- Neon PostgreSQL + Prisma 6
- Zustand for client state
- Deployed on Vercel

## Project Structure
- 70+ source files, ~12K lines of code
- 71 questions, 32 scenarios, 31 topics, 160 vocab items
- 24 routes (10 pages + 14 API endpoints)

## Database Models
User, PracticeSession, Score, TrainingData, UserProfile, UserMemory, Account, Session, VerificationToken

## 3 Modes
1. **Learn** — AI teacher Marie, voice+text, English translations, confidence boosters, streak counter
2. **Mock Test** — 3 tasks, hint panel, coaching, scoring, pep talks
3. **Real Exam** — Voice only, exact 12-min timing, strict examiner, timer pauses during AI speech

## Key Features
- VIP access codes (JASS1130/SONA0329) = free premium
- 6-minute free demo for non-premium users
- All conversations saved to TrainingData for future model training
- User profiles with progress tracking
- User memory system (vocabulary, grammar weaknesses)
- Results history with per-task breakdown
- Motivational quotes and confidence meter

## Known Issues Still To Fix (next session)
1. VIP code flow needs bypass — currently requires Clerk signup after code entry. Need code-only instant login.
2. Mock test English help bar at top (not yet added)
3. Answer memory/pattern system for mock test (not yet added)
4. Confidence meter visual (not yet added)
5. Quick vocabulary popup in mock test (not yet added)
6. Marketing layout mobile hamburger menu (added but untested)
7. Some Clerk text still dark on dark background (CSS overrides added but need testing)

## Env Vars Required
- NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY, CLERK_SECRET_KEY
- DATABASE_URL, DIRECT_URL (Neon)
- STRIPE_SECRET_KEY, NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY, STRIPE_WEBHOOK_SECRET
- GROQ_API_KEY, GEMINI_API_KEY
- NEXT_PUBLIC_APP_URL
- VALID_ACCESS_CODES (optional, defaults to JASS1130,SONA0329)

## Commands
- `npm run dev` — local dev (port 4000 works better than 3000)
- `npm run build` — production build
- `npx prisma db push` — sync schema to Neon
- `npx vercel --prod --yes` — deploy to Vercel
- `git push origin main` — push to GitHub
