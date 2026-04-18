---
title: "How to prepare your company for the era of agentic ITops"
date: 2026-04-17
source: "The New Stack"
link: "https://thenewstack.io/how-to-prepare-your-company-for-the-era-of-agentic-itops/"
categorie: "Engineering"
action: "keep"
pertinence: 3.5
contrarian: false
vendor_bias: true
uid: "85e6711151ca"
tags:
  - agentic-ai
  - itops
  - automation
  - knowledge-graph
  - NHI
  - access-control
---

# How to prepare your company for the era of agentic ITops

| | |
|---|---|
| **Pertinence** | 3.5/5 |
| **Catégorie** | Engineering / ITops |
| **Source** | [The New Stack](https://thenewstack.io/how-to-prepare-your-company-for-the-era-of-agentic-itops/) |

## Résumé

⚠️ **Contenu vendor** (BigPanda) mais insight architectural valide : les agents IA pour ITops échouent sans **unification data + knowledge**. Problème : les CMDBs et observability tools sont silotés, le tribal knowledge des équipes (runbooks, SOPs) n'est pas structuré. Solution proposée : IT Knowledge Graph fusionnant data sources + human knowledge + AI sensing. Cas d'usage : détection proactive, résolution sans escalade, réduction downtime. **Implication NHI** : les agents ITops manipulent access controls ("users properly provisioned"), donc credentials à haut privilège — aucune mention de scoping/rotation/audit.

Impact financier cité : "hundreds of billions of dollars" gaspillés en automation partielle.

## Actions recommandées

- [ ] **Livre : chapitre NHI** — Cas d'usage "agentic ITops" = agent avec accès CMDB + provisioning systems → high-privilege service account, besoin de scope limitation
- [ ] Challenger : si agent ITops a accès provisioning, comment garantir separation of duties (SoD) ? Conflict avec contrôles DORA/NIS2 ?
- [ ] Identifier équivalent non-vendor de "IT Knowledge Graph" — graph databases (Neo4j) + RAG pour runbooks ?
- [ ] **Question réglementation** : DORA exige traçabilité des changements critiques — un agent ITops auto-résolvant génère-t-il un audit trail conforme ?

---
## 📝 Notes personnelles

**Vendor bias** : -0.5 (article The New Stack sponsorisé BigPanda)

**Pertinence ajustée** : 3.5/5 (concept valide mais promo webinar masqué)

**Angle NHI critique** :
L'article dit "access controlled, users properly provisioned" — si l'agent fait ça, il a un service account avec droits IAM/provisioning. Questions :
- Scope : peut-il créer des comptes admin ?
- Rotation : les credentials de l'agent sont-ils rotatés ?
- Audit : chaque action est-elle tracée avec agent identity ?

**Lien réglementation** :
- DORA (EU) : Article 15 — ICT change management, traçabilité obligatoire
- NIS2 : Incident response automation doit respecter separation of duties
- Si agent ITops = "automated response", il entre dans le scope réglementaire

**Contrarian potentiel** :
Agentic ITops pourrait **violer** les principes Zero Trust si :
1. Agent a standing privileges (vs just-in-time)
2. Pas de continuous verification de l'agent lui-même
3. Aucune mention de "least privilege for agents"

→ Les agents doivent être soumis au même Zero Trust que les humains (Axiome #4 challengé indirectement)

**Pattern architectural** :
```
Traditional ITops: Human → CMDB/Observability → Manual correlation
Agentic ITops:    Agent → Knowledge Graph → Auto-resolution
```

Mais où est le control plane de l'agent ? Policy engine ? Token issuance ?
