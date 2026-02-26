---
title: "What happens to a database when the user is an AI agent"
date: 2026-02-25
source: "The New Stack"
link: "https://thenewstack.io/databases-for-ai-agents/"
categorie: "Architecture"
action: keep
pertinence: 4.0
contrarian: false
vendor_bias: false
uid: "https://thenewstack.io/databases-for-ai-agents/"
tags:
  - ai-agents
  - non-human-identity
  - database
  - api-security
  - nhi
---

# What happens to a database when the user is an AI agent

| | |
|---|---|
| **Pertinence** | 4/5 |
| **Catégorie** | Architecture |
| **Source** | [The New Stack](https://thenewstack.io/databases-for-ai-agents/) |

## Résumé
Lorsque l'utilisateur d'une base de données est un agent IA plutôt qu'un humain, les hypothèses fondamentales sur l'accès aux données, la gouvernance et l'autorisation s'effondrent. Les agents IA génèrent des patterns de requêtes imprévisibles, à haute fréquence, potentiellement non bornés — remettant en cause les modèles de contrôle d'accès traditionnels (RBAC, quotas humains). L'article soulève des questions critiques pour l'identité non-humaine (NHI) : comment authentifier, autoriser et auditer un agent IA accédant à des datastores sensibles ? Les implications pour les secteurs réglementés (banque, santé) sont directes : les API Gateways et Authorization Servers doivent gérer des identités machine à sémantique comportementale variable.

## Actions recommandées
- [ ] Mapper les patterns d'accès AI agent sur le modèle NHI existant : credential lifecycle, scope minimization, audit trail
- [ ] Évaluer si les Authorization Servers actuels (AS dédiés type Keycloak/Auth0/Cerbos) supportent des politiques dynamiques pour agents IA
- [ ] Inclure ce cas d'usage dans le chapitre "Non-Human Identity" du livre "Securing APIs in the Age of AI Agents"
- [ ] Analyser les implications RGPD/réglementaires quand un agent IA accède à des données de santé ou bancaires via API

---
## 📝 Notes personnelles
