---
title: "Databases weren't built for agent sprawl – SurrealDB wants to fix it"
date: 2026-02-25
source: "The New Stack"
link: "https://thenewstack.io/surrealdb-3-ai-agents/"
categorie: "Architecture"
action: keep
pertinence: 3.5
contrarian: false
vendor_bias: true
uid: "https://thenewstack.io/surrealdb-3-ai-agents/"
tags:
  - ai-agents
  - database
  - state-management
  - agent-architecture
---

# Databases weren't built for agent sprawl – SurrealDB wants to fix it

| | |
|---|---|
| **Pertinence** | 3.5/5 |
| **Catégorie** | Architecture |
| **Source** | [The New Stack](https://thenewstack.io/surrealdb-3-ai-agents/) |

## Résumé
L'article soulève un angle architectural souvent ignoré : les agents IA génèrent des besoins de state management hybrides (transactionnel + graphe + vectoriel) que les bases de données traditionnelles ne couvrent pas. La fragmentation du state entre plusieurs stores crée des surface d'attaque supplémentaires et complique l'audit trail — problème direct pour les secteurs régulés. SurrealDB positionne une approche unifiée, mais l'article est fortement orienté vendor. L'insight architectural sur le "agent sprawl" et ses implications sur la cohérence des sessions d'autorisation est pertinent pour un chapitre sur les architectures agentiques sécurisées.

## Actions recommandées
- [ ] Cartographier les types de state qu'un agent bancaire doit persister et leur classification de sensibilité
- [ ] Évaluer l'impact de la fragmentation des stores sur l'auditabilité réglementaire (DSP2, DORA)

---
## 📝 Notes personnelles
<!-- Angle sécurité : chaque store supplémentaire = surface d'attaque + complexité IAM. Vendor bias marqué (SurrealDB), à recouper avec des sources neutres. -->