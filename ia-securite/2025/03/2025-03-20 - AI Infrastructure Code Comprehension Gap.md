---
title: "AI can write your infrastructure code. There's a reason most teams won't let it."
date: 2025-03-20
source: "The New Stack"
link: "https://thenewstack.io/spacelift-ai-infrastructure-code/"
categorie: "ia-securite"
action: "keep"
pertinence: 4.0
contrarian: false
vendor_bias: true
uid: "912ca79cfc8a"
tags:
  - ai-agents
  - infrastructure-as-code
  - guardrails
  - llm-security
  - spacelift
  - opentofu
  - non-human-identity
---

# AI can write your infrastructure code. There's a reason most teams won't let it.

| | |
|---|---|
| **Pertinence** | 4.0/5 |
| **Catégorie** | IA & Sécurité |
| **Source** | [The New Stack](https://thenewstack.io/spacelift-ai-infrastructure-code/) |

## Résumé

⚠️ **Contenu vendor** — Interview de Marcin Wyszynski (Spacelift, OpenTofu) sur le paradoxe de l'IA en IaC : les LLMs écrivent désormais tout le code HCL, mais **les équipes refusent de les laisser déployer en production** à cause du "comprehension gap" (métaphore du phrasebook portugais : tu peux poser la question, pas comprendre la réponse). **Insight clé : le risque IaC != risque app** (rollback app = facile, rollback infra = perte DB potentielle). La solution Spacelift : guardrails déterministes (OPA policies) + contexte organisationnel injecté, pas "LLM qui vérifie LLM". **Transposable aux API agents & NHI** : même problème de délégation de pouvoir sous contrainte.

## Actions recommandées

- [ ] **Intégrer la métaphore "Portuguese phrase book"** dans le chapitre du livre sur les limites des AI agents pour les APIs critiques
- [ ] Étudier l'approche "deterministic guardrails" (OPA) vs "LLM-based validation" : pattern applicable aux API authorization policies pour agents IA
- [ ] Analyser le modèle Spacelift Intent (LLM query cloud schemas directly) : quel équivalent pour les agents appelant des APIs bancaires ? → Policy-aware API discovery
- [ ] Challenger l'axiome "humans are non-deterministic too" : est-ce que les guardrails humains (code review, change control) sont vraiment transposables 1:1 aux LLMs ?

---

## 📝 Notes personnelles

**Angle fort** : Le "comprehension gap" est une excellente façon de formuler le problème de confiance dans les systèmes autonomes. Ce n'est PAS un problème de compétence (le LLM sait écrire du code correct), c'est un problème d'**auditabilité et de blast radius**.

**Lien direct avec NHI** :
- Un LLM qui provisionne de l'infra = une machine identity avec des privilèges élevés
- Les "guardrails déterministes" = policies ABAC/RBAC pour service accounts
- Le besoin de "context injection" (existing projects, reusable modules) = même problème que les agents IA qui doivent comprendre les contraintes métier avant d'appeler une API de virement

**Pattern transposable aux APIs bancaires** :
- **Stupid** (console clics) = appels API directs sans audit trail
- **Ceremonial** (full IaC review) = workflow d'approbation multi-niveaux qui ralentit tout
- **Intent-based** (Spacelift) = agent IA qui propose une action, guardrails OPA qui valident en temps réel, capture en IaC pour audit a posteriori

→ Équivalent API : agent IA génère un payment intent, policy engine vérifie compliance (montant, bénéficiaire whitelist, velocity), exécute, log immutable pour audit.

**Contrarian potentiel** : L'article assume que "LLMs need guardrails like humans do", mais c'est faux. Les humains ont du **contexte implicite** (culture org, sens commun, capacité à escalader en cas de doute). Les LLMs ont besoin de **contexte explicite et exhaustif**. Le modèle de guardrails n'est pas identique, il est plus rigide et fragile.

**Vendor bias** : Spacelift vend Intent, donc l'article est orienté. Mais l'insight reste valide.

---

## 📝 Opportunité éditoriale (score: 7/10)

**Thème** : AI Agents & Infrastructure Risk  
**Angle** : Le "comprehension gap" n'est pas un problème technique, c'est un problème de blast radius.

> 🪝 Hook : "Your AI can write perfect code. That's not the problem. The problem is you can't understand its answer when things go wrong."

**Points clés** :
1. La métaphore du phrasebook : compétence ≠ comprehension
2. Pourquoi le risque IaC > risque app (irréversibilité, blast radius)
3. Guardrails déterministes > LLM self-validation
4. Transposition aux API agents : même problème, mêmes solutions

**Question ouverte** : "If humans are non-deterministic too, why do we trust them more than LLMs? Is it because they can explain their reasoning, or because they're liable?"

**Angle contrarian** : "We're building guardrails for AI like we build them for humans. That's the wrong model."

**Hashtags** : #AIAgents #APISecurity #InfrastructureAsCode #ZeroTrust #NonHumanIdentity #PolicyAsCode

