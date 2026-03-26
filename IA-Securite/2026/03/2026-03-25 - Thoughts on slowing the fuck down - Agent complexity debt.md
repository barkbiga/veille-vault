---
title: "Thoughts on slowing the fuck down - Agent complexity debt"
date: 2026-03-25
source: "Simon Willison's Weblog"
link: "https://simonwillison.net/2026/Mar/25/thoughts-on-slowing-the-fuck-down/#atom-everything"
categorie: "IA-Securite"
action: "keep"
pertinence: 5.0
contrarian: true
vendor_bias: false
uid: "d7540301156e"
tags:
  - AI-agents
  - architecture
  - cognitive-debt
  - NHI
  - code-generation
  - risk-management
  - contrarian
---

# Thoughts on slowing the fuck down - Agent complexity debt

| | |
|---|---|
| **Pertinence** | 5/5 |
| **Catégorie** | IA-Securite |
| **Source** | [Simon Willison's Weblog](https://simonwillison.net/2026/Mar/25/thoughts-on-slowing-the-fuck-down/#atom-everything) |

## Résumé

🔄 **CONTRARIAN** — Mario Zechner (créateur du Pi agent framework) critique frontalement l'adoption débridée des agents IA en développement. **Thèse centrale** : les agents génèrent de la complexité à une vitesse qui dépasse notre capacité cognitive à maintenir la cohérence architecturale. Sans discipline, on crée une "dette cognitive" insoutenable. **Recommandation radicale** : limiter volontairement la quantité de code généré par jour, écrire à la main tout ce qui définit l'architecture/API. **Lien direct NHI** : les agents sont des non-human identities non maîtrisées, "marchands de complexité" auxquels on délègue l'agence sans contrôle.

## Actions recommandées

- [ ] **Livre AI Agents** : Intégrer cette perspective dans le chapitre gouvernance/risques — la vélocité des agents comme surface d'attaque architecturale
- [ ] **Framework NHI** : Traiter les agents génératifs comme des identités à risque élevé nécessitant audit systématique des changements (code review humain obligatoire)
- [ ] **Politique interne** : Définir des "quotas de complexité" pour les contributions agent (ex: max X KLOC/jour, review obligatoire sur architecture/API)
- [ ] **Post LinkedIn** : "Les agents IA sont-ils les nouveaux comptes de service non audités ? Parallèle entre dette technique et dette cognitive"

---

## 📝 Opportunité éditoriale (score: 8/10)

**Thème** : Gouvernance des agents IA comme problème de gestion d'identité non-humaine

**Angle** : Les DevOps ont mis 10 ans à maîtriser les service accounts. On reproduit les mêmes erreurs avec les agents IA en 10 mois.

> 🪝 Hook : "En 2016, on découvrait que 40% des identités AWS étaient des bots non audités. En 2026, combien de vos PRs sont reviewées par des humains qui comprennent réellement le code ?"

**Points clés** :
1. Mario Zechner (créateur Pi framework) alerte : "Vous avez délégué toute votre agence aux agents. Vous n'avez plus aucune idée de ce qui se passe."
2. Le problème n'est pas la qualité du code généré, mais la **vitesse d'accumulation** de micro-décisions architecturales non intentionnelles
3. "Cognitive debt" = nouveau vecteur de risque — quand la vélocité dépasse la compréhension, on perd le contrôle

**Question ouverte** : Faut-il traiter les agents IA comme des identités privilégiées dans votre matrice de risque IAM ? Quotas, audit trails, principe du moindre privilège ?

**Angle contrarian** : Contre le narrative "ship faster with AI" — plaidoyer pour des limites volontaires, friction intentionnelle

**Hashtags** : #AIAgents #NonHumanIdentity #ZeroTrust #CognitiveSecurity #TechDebt #IAM

---

## 📝 Notes personnelles

**Connexion IAM/CIAM** : Les agents IA sont des NHI avec un périmètre d'action (scope) souvent indéfini. Contrairement à un service account avec des permissions API limitées, un agent de génération de code a potentiellement accès à l'ensemble du système architectural. C'est l'équivalent d'un compte root sans MFA.

**Challenge axiome #4** : "L'identité est le nouveau périmètre de sécurité" — oui, mais si les identités elles-mêmes génèrent de l'opacité cognitive, le périmètre devient imperméable dans les deux sens. On ne peut pas sécuriser ce qu'on ne comprend plus.

**Proposition framework** :
- **Agent Privilege Levels** (APL) : READ (doc), SUGGEST (review requis), WRITE (scope limité), ARCHITECT (interdit ou humain-in-loop obligatoire)
- **Agent Activity Monitoring** : Trace complète des modifications avec diff sémantique (pas juste git blame)
- **Cognitive Load Budget** : Métrique d'équipe — nb de fichiers modifiés/jour * complexité cyclomatique vs capacité review

**Angle livre** : Chapitre "Agent Identity Governance" — traiter les agents comme des insider threats potentiels. Pas par malveillance, mais par volume. Le ransomware de demain sera peut-être un agent bien intentionné qui aura refactoré votre codebase en 48h sans que personne ne comprenne les invariants cassés.

**Référence croisée** : Rappelle le débat "feature flags vs branches" — la vélocité nécessite des safety rails, pas leur suppression.
