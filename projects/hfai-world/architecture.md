# HFAi.world — architecture.md

## 1) Purpose
HFAi.world is the public “World Shell” of the HFAi universe:
- cinematic, navigable, experiential
- showcases personas, labs, prompt engine, and portals
- designed to evolve into a deeper authenticated world at: app.hfai.world

This file defines the architecture, repo roles, and integration strategy.

---

## 2) Repo Strategy (Source of Truth vs Deployment)

### 2.1 Source of Truth
**HFAi-Core** is the canonical repository.
All blueprints, rules, UX intent, content structure, and system canon live here:
- /docs (rules + canon)
- /projects/hfai-world (product definition + structure + specs)
- /prompts (reusable prompt systems)
- /templates (schemas and templates)

### 2.2 Deployment Repo (Optional / Recommended later)
A separate repo (e.g., **hfai-world**) may exist ONLY as a deployment/execution repository:
- contains actual site code (HTML/JS or Next.js)
- has hosting/deploy pipelines (Vercel/Netlify/Hostinger)
- must stay aligned with HFAi-Core specs

**Rule:** If there is any conflict, HFAi-Core wins.

---

## 3) Product Layers

### 3.1 Public Shell (Phase 1)
- cinematic entry
- universe map navigation
- personas preview directory
- Omni-Prompt Engine demo (prompt architecture, not “execution”)
- Labs (at least Lab 01 live demo)
- Vault preview (localStorage now, real DB later)
- Portals to other domains
- Support + License

### 3.2 Authenticated World (Phase 2+)
- accounts
- real vault storage
- permissions + projects
- persona rooms with deeper interactions
- analytics + personalization

---

## 4) Module Architecture (Feature Blocks)

### Required Modules (Phase 1)
- Universe Map (clickable planets + transitions)
- Magic Lens (global quick access + selectors + preview + route)
- Audio System (persistent across navigation)
- Data Catalogs (Personas / Knowledge Teams / Application Teams)
- Labs Demo (Gemini via serverless proxy)
- Vault Preview (localStorage + export pack)

### Optional Modules (Phase 1.5 / Phase 2)
- Voice Input + Voice Output
- Realtime persona conversations
- Registration + database-backed accounts
- Marketplace/payment flows (later)

---

## 5) AI + Voice Integration (Safe by Design)

### 5.1 Gemini / AI Calls
Never call Gemini directly from the browser.
Use a serverless proxy:
- /api/generate (serverless function)
- stores API keys in server environment
- rate limits and logging
- returns safe, formatted outputs

### 5.2 Voice (Progressive Enhancement)
Phase 1:
- Web Speech API in browser:
  - SpeechRecognition (input)
  - SpeechSynthesis (output)
- fallback to text always

Phase 2:
- server-side voice (higher quality TTS/STT)
- persona-context routing + moderation

---

## 6) Persistent Audio Architecture
Goal: background soundtrack should not restart on every navigation.

Preferred approach:
- Single Page App routing (Next.js) OR
- if static multi-page: store and restore audio position/state using localStorage:
  - currentTime
  - muted
  - playing state
Then resume after navigation.

---

## 7) Folder Structure (Canonical in HFAi-Core)

Inside: /projects/hfai-world
- vision.md (north star)
- sitemap.md (page map)
- architecture.md (this file)
- pages/ (page blueprints)
- copy/ (microcopy + bilingual copy packs)
- design/ (visual tokens, UI rules, motion rules)
- tech/ (stack decision + deployment notes)

---

## 8) Definition of Done (Phase 1 Launch)
A visitor can:
- enter the world shell
- navigate universe map to key sections
- view personas and teams (clean, non-exploitable descriptions)
- run Lab 01 demo
- save output to Vault preview
- use Magic Lens to jump anywhere
- keep audio playing across navigation
- see portals + contact support

---

## 9) Governance Rules
- No “zip-only” deliverables. Any change must be committed to GitHub.
- Any new feature must be added as a module and documented here first.
- No secrets in frontend. Keys only in serverless secrets.
