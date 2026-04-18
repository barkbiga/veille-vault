---
title: "Join us at PyCon US 2026 in Long Beach - AI and security tracks"
date: 2026-04-17
source: "Simon Willison"
link: "https://simonwillison.net/2026/Apr/17/pycon-us-2026/#atom-everything"
categorie: "IA"
action: "borderline"
pertinence: 2.5
contrarian: false
vendor_bias: false
uid: "244a4bb327a7"
tags:
  - pycon
  - ai-agents
  - async-patterns
  - voice-agents
  - edge-inference
  - conference
---

# Join us at PyCon US 2026 in Long Beach — AI and security tracks

| | |
|---|---|
| **Pertinence** | 2.5/5 |
| **Catégorie** | IA / Conférence |
| **Source** | [Simon Willison](https://simonwillison.net/2026/Apr/17/pycon-us-2026/#atom-everything) |

## Résumé

PyCon US 2026 (15-17 mai, Long Beach) introduit deux nouvelles tracks dédiées : AI (vendredi) et Security (samedi). Track chairs : Silona Bonewald (CitableAI) et Zac Hatfield-Dodds (Anthropic). **Signal faible** : convergence explicite AI+Security dans une conf mainstream Python. Talks pertinents : "Don't Block the Loop: Python Async Patterns for AI Agents" (patterns async pour agents), "How to Build Your First Real-Time Voice Agent" (voice agents), "Distributing AI with Python in the Browser" (edge inference). Simon Willison animera des open spaces sur Datasette et agentic engineering.

Pertinence limitée (annonce événement) mais **indicateur de maturité** : les agents IA sortent du hype, entrent dans l'ingénierie mainstream avec focus sécurité.

## Actions recommandées

- [ ] **Veille post-conférence** : récupérer slides/vidéos des talks "Async Patterns for AI Agents" et "Voice Agent" — patterns directement applicables à agent authentication/authorization
- [ ] Suivre les open spaces Simon Willison sur agentic engineering (probablement livetweetés) — insights pratiques sur agent workflows
- [ ] **Livre** : Si talk "Voice Agent" couvre authentication flow (user → voice agent → backend API), citer comme cas d'usage OAuth delegation
- [ ] Challenger track Security : quels sujets agent identity vs sécurité applicative classique ?

---
## 📝 Notes personnelles

**Borderline** car annonce événement, mais signaux intéressants :

**Convergence AI+Security** :
Fait notable : PyCon (conf généraliste) crée une track Security l'année où elle crée une track AI. Implique que la communauté Python reconnaît les risques sécurité des agents.

**Talks à surveiller** :
1. **"Async Patterns for AI Agents"** (Aditya Mehra) — agents long-running = session management, token refresh, credential lifecycle
2. **"Voice Agent"** (Camila Hinojosa, Elizabeth Fuentes) — authentication flow : user voice → agent → API calls avec quels credentials ?
3. **"Edge Inference"** (Fabio Pliger) — si LLM en edge (browser), où sont les API keys ? Client-side credentials = anti-pattern

**Lien NHI** :
Voice agents = machine identity avec délégation user. Équivalent : OAuth device flow ? Ou agent a son propre identity ?

**Open spaces potentiels** (si j'y étais) :
- "Agent credentials: OAuth, API keys, or something new?"
- "Zero Trust for AI agents: feasible or fantasy?"
- "Auditing agent actions: liability and compliance"

**Score pertinence** : 2.5/5
- Culture/signaux faibles : +2
- Pas de contenu technique immédiat : pas de bonus
- Potentiel futur (vidéos) : intéressant mais pas actionnable maintenant
