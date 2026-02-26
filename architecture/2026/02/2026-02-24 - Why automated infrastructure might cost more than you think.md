---
title: "Why \"automated\" infrastructure might cost more than you think"
date: 2026-02-24
source: "The New Stack"
link: "https://thenewstack.io/automated-infrastructure-hidden-costs/"
categorie: "Architecture"
action: borderline
pertinence: 2.0
contrarian: false
vendor_bias: false
uid: "https://thenewstack.io/automated-infrastructure-hidden-costs/"
tags:
  - infrastructure
  - automation
  - platform-engineering
  - technical-debt
---

# Why "automated" infrastructure might cost more than you think

| | |
|---|---|
| **Pertinence** | 2/5 |
| **Catégorie** | Architecture |
| **Source** | [The New Stack](https://thenewstack.io/automated-infrastructure-hidden-costs/) |

## Résumé
L'article pointe les coûts cachés de l'automatisation infrastructure — jobs Jenkins hérités, dettes opérationnelles masquées par l'apparente fiabilité des pipelines. Pertinence périphérique pour la sécurité API : les pipelines CI/CD automatisés portent des secrets (credentials NHI) souvent non rotés, mal gouvernés. La dette d'automatisation est aussi une dette de sécurité des identités non-humaines. Connexion indirecte mais réelle avec le chapitre NHI du livre.

## Actions recommandées
- [ ] Audit des pipelines CI/CD comme vecteur NHI : secrets exposés, tokens de longue durée, absence de rotation
- [ ] Lier à la problématique de gouvernance des NHI dans les environnements hautement automatisés

---
## 📝 Notes personnelles
