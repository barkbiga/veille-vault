---
title: "Why long-running AI agents break on HTTP and how Ably is fixing it"
date: 2026-05-06
source: "The New Stack"
link: "https://thenewstack.io/ably-durable-sessions-ai/"
categorie: "Infrastructure"
action: "keep"
pertinence: 4.0
contrarian: false
vendor_bias: true
uid: "49c59d097185"
tags:
  - AI-agents
  - infrastructure
  - protocols
  - HTTP
  - durable-sessions
  - state-management
---

# Ably durable sessions for long-running AI agents

| | |
|---|---|
| **Pertinence** | 4/5 |
| **Catégorie** | Infrastructure |
| **Source** | [The New Stack](https://thenewstack.io/ably-durable-sessions-ai/) |

⚠️ Contenu vendor (Ably CEO), mais insight architectural solide sur l'émergence d'une nouvelle couche infrastructure.

## Résumé

Interview Matthew O'Riordan (CEO Ably) sur l'émergence des "durable sessions" comme primitive infrastructure pour agents IA long-running. **Problème** : HTTP est parfait pour one-shot completions mais inadapté aux agents qui raisonnent pendant des heures avec des dizaines de tool calls. Les utilisateurs attendent désormais l'expérience ChatGPT : switch entre tabs/devices et retrouver l'état synchronisé. **Solution architecturale** : durable sessions = streams + presence + shared state + storage pour rehydratation + push notifications offline. Ably étend ses primitives (messages mutables pour token streaming, "live objects" pour état partagé). Le terme "durable sessions" popularisé par ElectricSQL (vs "durable streams" d'EMQX). Pattern d'adoption : garder requête client→agent sur HTTP (où devs sont déjà), basculer seulement la réponse sur session durable. Vercel AI SDK et TanStack exposent déjà des abstractions de transport pour ce layer.

## Actions recommandées

- [ ] **Évaluer need** : nos use cases APIs nécessitent-ils des sessions durables (long-running) ou HTTP suffit (transactionnel) ?
- [ ] **Pattern exploration** : tester Vercel AI SDK avec transport durable sur un POC agent bancaire
- [ ] **Trade-off analysis** : coût/complexité durable sessions vs expérience utilisateur agent long-running
- [ ] **State management** : si adoption, définir stratégie pour "live objects" partagés agent/humain (CRDT, event sourcing ?)
- [ ] **Documentation** : si pertinent, ajouter section "Agent Session Management" dans guide API banking

---

## 📝 Notes personnelles

**Lien avec le livre** :
- Chapitre infrastructure agents → nouvelle couche "durable session layer" à cartographier
- Analogie : durable sessions pour agents = ce que WebSocket a été pour real-time web

**Insights architecturaux** :
- **Vocabulaire émergent** : "durable sessions" > "durable streams" (sessions = streams + state + presence + storage)
- **Stratégie adoption** : hybrid approach (HTTP in, session out) → friction minimale pour devs
- **Frameworks support** : Vercel AI SDK et TanStack ont déjà des abstractions → standard de facto en formation

**Questions architecturales** :
- **Sécurité** : session durable = session longue → comment gérer rotation credentials sans casser la session ?
- **Compliance** : agent bancaire avec session de 4h → logs, audit trail, DORA requirements ?
- **Fallback** : que se passe-t-il si le durable session provider (Ably, etc.) a une outage ?

**Vendor bias détecté** :
- Article positionne Ably comme solution, mais le concept de durable sessions est plus large
- Mention EMQX (MQTT broker) et ElectricSQL → crédibilité renforcée (pas juste self-promo)
- Abstractions dans Vercel/TanStack = validation indépendante du pattern

**Pattern émergent** :
- Les frameworks d'agents intègrent des transport abstractions → nouvelle couche dans stack
- Ably "trillions of transactions/month" pour HubSpot/Intercom → scale prouvé, pas vaporware

**Connexion Zero Trust** :
- Session durable multi-device = challenge pour Zero Trust (continuous verification sur session de 4h ?)
- Besoin de re-authentication périodique ou continuous risk scoring pendant la session ?
