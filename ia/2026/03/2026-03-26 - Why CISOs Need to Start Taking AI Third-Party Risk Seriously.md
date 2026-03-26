---
title: "Why CISOs Need to Start Taking AI Third-Party Risk Seriously"
date: 2026-03-26
source: "BankInfoSecurity"
link: "https://www.bankinfosecurity.com/cisos-need-to-start-taking-ai-third-party-risk-seriously-a-31190"
categorie: "IA"
action: keep
pertinence: 4.0
contrarian: false
vendor_bias: false
uid: "https://www.bankinfosecurity.com/cisos-need-to-start-taking-ai-third-party-risk-seriously-a-31190"
tags:
  - agentic-ai
  - third-party-risk
  - NHI
  - identity-controls
  - financial-services
  - LLM
---

# Why CISOs Need to Start Taking AI Third-Party Risk Seriously

| | |
|---|---|
| **Pertinence** | 4/5 |
| **Catégorie** | IA |
| **Source** | [BankInfoSecurity](https://www.bankinfosecurity.com/cisos-need-to-start-taking-ai-third-party-risk-seriously-a-31190) |

## Résumé
David Cass, CISO chez Keyrock (institution financière crypto-native), alerte sur l'inadéquation des modèles classiques de gouvernance face aux LLMs et aux systèmes d'IA agentique. Le cœur du problème : les agents IA créent des identités non-humaines dynamiques, invisibles dans les inventaires d'assets traditionnels, et opèrent avec des permissions opaques via des tiers (providers LLM, outils MCP, etc.). Il insiste sur trois angles critiques : accountability (qui est responsable si un agent IA tiers exfiltre des données ?), asset visibility (les credentials machine des agents ne sont pas trackés dans les CMDB classiques), et identity controls (les LLMs appellent des APIs avec des tokens dont le scope est rarement gouverné). Angle particulièrement pertinent : le tiers-party risk appliqué à l'IA sort du cadre DORA classique — les SLA et audits fournisseurs ne couvrent pas la non-déterminisme des modèles.

## Ce que ça casse / remet en question
- **Axiome #4 challengé en creux** : "L'identité est le nouveau périmètre" — oui, mais si l'identité de l'agent IA est gérée par un tiers opaque (OpenAI, Anthropic, provider LLM), le périmètre identitaire échappe structurellement à l'organisation. L'axiome est partiellement faux quand l'identité est déléguée à un tiers.
- Connexion directe livre : chapitre NHI & agent identity — les agents agentiques comme nouvelle classe de NHI avec un tiers-party risk spécifique.

## Actions recommandées
- [ ] Intégrer le cas "agent IA tiers" dans le chapitre NHI du livre — modéliser l'identité d'un agent LLM comme une workload identity avec délégation externe
- [ ] Croiser avec les exigences DORA ICT third-party risk (Art. 28-30) : les providers LLM entrent-ils dans le scope des CTPP ?
- [ ] Préparer un post LinkedIn : "Votre provider LLM est-il un tiers critique DORA ?"

---
## Notes personnelles
