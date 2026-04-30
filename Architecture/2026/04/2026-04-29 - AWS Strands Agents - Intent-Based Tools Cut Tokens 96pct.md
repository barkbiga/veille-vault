---
title: "Cut AI token usage by 96%? Here's how AWS Strands Agents does it"
date: 2026-04-29
source: "The New Stack"
link: "https://thenewstack.io/strands-agents-tool-design/"
categorie: "Architecture"
action: "keep"
pertinence: 4.5
contrarian: false
vendor_bias: true
uid: "acabd79e962f"
tags:
  - AWS-Strands
  - Intent-Based-Tools
  - Token-Optimization
  - MCP
  - Agent-Design
  - API-Gateway
  - Semantic-Search
---

# Cut AI token usage by 96%? Here's how AWS Strands Agents does it

| | |
|---|---|
| **Pertinence** | 4.5/5 |
| **Catégorie** | Architecture |
| **Source** | [The New Stack](https://thenewstack.io/strands-agents-tool-design/) |

## Résumé

⚠️ **Contenu vendor (AWS)** mais données chiffrées solides. **Demo AWS Strands** par Morgan Willis : 3 itérations pour récupérer "dernière facture client". (1) **Direct API mapping** (1 endpoint = 1 tool) → 5 appels chaînés, 52k tokens. (2) **Intent-based tools** (outcome-driven, pas data-driven) → 1 appel, 2k tokens (**96% de réduction**). L'intent-based tool encapsule plusieurs API calls mais expose une seule intention à l'agent. (3) **MCP + semantic search** → tools servis via MCP server, semantic search filtre le catalogue, divise encore tokens par 2. **Principe clé** : "Agents étroitement scopés > agents génériques". Moins de tools exposés = moins d'erreurs. Pattern : many narrow agents > one general agent.

## Actions recommandées

- [ ] Évaluer pattern "intent-based tools" pour APIs bancaires — masquer complexité orchestration à l'agent
- [ ] Analyser MCP + semantic search comme pattern de gouvernance pour catalogues API (PSD2, open banking)
- [ ] Challenger axiome #3 : si l'agent accède via Gateway+MCP, l'Authorization Server dédié est-il encore pertinent ?
- [ ] Quantifier coût token pour agents banking en production — 96% réduction change l'équation économique

---
## 📝 Opportunité éditoriale (score: 6/10)

**Thème** : L'architecture des tools agent détermine le coût ET la précision
**Angle** : Pourquoi exposer 16 APIs à votre agent est une erreur — même si elles sont toutes pertinentes

> 🪝 Hook : AWS a réduit l'utilisation de tokens de 96% pour la même tâche. Pas en optimisant le modèle — en repensant comment l'agent voit les APIs.

**Points clés** :
1. Mapping direct (1 API = 1 tool) → 52k tokens, 5 appels chaînés
2. Intent-based tools (outcome-driven) → 2k tokens, 1 appel
3. MCP + semantic search → divise encore par 2
4. "The fewer tools you expose, the less likely it is to call the wrong one"

**Question ouverte** : Si vos agents bancaires appellent les mauvaises APIs 30% du temps, est-ce un problème d'IA ou d'architecture ?

**Hashtags** : #AgentArchitecture #APISecurity #TokenOptimization #MCP #IntentBasedDesign

---
## 📝 Notes personnelles

**Vendor bias évident (AWS Strands)** mais le pattern est généralisable et les chiffres sont exploitables.

**Pattern CORE pour le livre** : Intent-based tools vs direct API mapping. C'est exactement le débat authorization : fine-grained permissions vs coarse-grained scopes.

**Lien axiome #3** : "Authorization Servers dédiés > features IAM dans Gateway". Mais si l'agent accède via Gateway qui fait semantic search sur tools MCP, l'AS dédié ajoute-t-il encore de la valeur ou devient-il un hop inutile ?

**Question économique** : 96% de réduction de tokens = 96% de réduction de coût. Pour un agent banking en production (1M appels/jour), ça passe de $X00k à $X0k/mois. **Game changer** pour business case agents.

**Signal architectural fort** : "Many narrow agents > one general agent". C'est le **microservices pattern appliqué aux agents**. Chaque agent = bounded context, catalog de tools scopé, surface d'erreur réduite.

**MCP devient incontournable** : 2e article aujourd'hui qui mentionne MCP (Model Context Protocol) comme standard émergent. À surveiller — pourrait devenir aussi structurant que OAuth.

**Trade-off implicite** : Intent-based tools = moins de flexibilité. Si le use case change légèrement, faut recoder le tool. Direct mapping = flexible mais coûteux. Pattern classique abstraction vs performance.
