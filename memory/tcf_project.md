---
name: TCF Speaking Prep AI Project
description: AI-powered TCF Canada speaking exam prep — live voice AI, 3 modes, $49.99/mo, VIP codes, Vercel deployed
type: project
---

**Location:** `C:/Users/xsjas/Desktop/tcf-prep/`
**GitHub:** https://github.com/xsjass/tcf-speaking-prep-ai (private)
**Live:** https://tcf-prep.vercel.app
**Settings backup:** https://github.com/xsjass/claude-settings-backup

## Tech Stack
- Next.js 15 + TypeScript + Tailwind CSS + Framer Motion
- Clerk Auth (Google + email) + VIP code-only login (JASS1130, SONA0329 bypass Clerk entirely)
- Stripe $49.99/month subscription
- Groq (Llama 3.3 70B) + Google Gemini (free, auto-fallback)
- Edge TTS + Google Translate TTS + Browser SpeechSynthesis (all free)
- Web Speech API for STT (free, unlimited)
- Neon PostgreSQL + Prisma 6
- Zustand for client state
- Deployed on Vercel

## VIP Code Flow (FIXED)
1. Enter code on /sign-in → calls /api/auth/code-login
2. Server creates VIP user + sets tcf-vip-token cookie (JWT, 365 days)
3. window.location.href = "/dashboard" — instant redirect
4. Middleware sees VIP cookie → skips Clerk → allows access
5. App layout sees VIP cookie → premium = true → no demo timer

## Database Models
User, PracticeSession, Score, TrainingData, UserProfile, UserMemory, Account, Session, VerificationToken

## Known Issues To Fix (next session)
1. Mock test English help bar at top (not yet added)
2. Answer memory/pattern system for mock test (not yet added)
3. Confidence meter visual (not yet added)
4. Quick vocabulary popup in mock test (not yet added)
5. Overall UI polish needed — make Learn/Mock/Exam more advanced and smooth
6. Some Clerk text still dark on dark background in certain views
7. Marketing layout mobile hamburger menu needs testing

## Commands
- `npm run dev --port 4000` — local dev
- `npm run build` — production build
- `npx prisma db push` — sync schema to Neon
- `npx vercel --prod --yes` — deploy to Vercel
- `git push origin main` — push to GitHub

## What User Says "load project TCF" Means
Continue from this exact state. Read this memory file, check GitHub repo, and pick up where we left off.
