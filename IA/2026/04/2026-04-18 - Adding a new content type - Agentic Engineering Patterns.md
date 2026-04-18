---
title: "Adding a new content type to my blog-to-newsletter tool"
date: 2026-04-18
source: "Simon Willison"
link: "https://simonwillison.net/guides/agentic-engineering-patterns/adding-a-new-content-type/#atom-everything"
categorie: "IA"
action: "keep"
pertinence: 4.5
contrarian: false
vendor_bias: false
uid: "9e25f81dfa8f"
tags:
  - agentic-engineering
  - prompt-patterns
  - coding-agents
  - claude
  - testing-automation
  - NHI
---

# Adding a new content type to my blog-to-newsletter tool

| | |
|---|---|
| **Pertinence** | 4.5/5 |
| **Catégorie** | IA / Agentic Engineering |
| **Source** | [Simon Willison](https://simonwillison.net/guides/agentic-engineering-patterns/adding-a-new-content-type/#atom-everything) |

## Résumé

Simon Willison dévoile un pattern d'ingénierie agentique hautement efficace : un prompt court (3 lignes) qui génère une solution complète en un seul coup. Le pattern révèle trois techniques clés pour maximiser l'autonomie des coding agents : (1) **clonage de référence isolé** (`/tmp` pour éviter pollution du commit), (2) **réutilisation de patterns existants** (imiter la logique Atom feed plutôt que la décrire), (3) **validation autonome** avec outils auto-documentés (`uvx rodney --help` enseigne l'agent). Résultat : modification SQL précise filtrant beats par description, sans intervention humaine. Implique la capacité des agents à gérer contexte multi-repos + auto-test.

**Pertinent pour NHI** : les coding agents accèdent à des repos GitHub (credentials), modifient du code manipulant des API (Datasette), et s'auto-valident — questions implicites d'identité machine et de délégation de credentials.

## Actions recommandées

- [ ] **Livre : chapitre NHI** — Intégrer ce cas d'usage comme exemple de "agent credentials in development workflows" : l'agent a besoin d'accès GitHub, d'exécution locale, de fetch HTTP (newsletter endpoint)
- [ ] Tester le pattern "clone to /tmp for reference" dans nos workflows internes — anti-pattern de pollution de commits
- [ ] Documenter pattern "self-validation with uvx --help" pour agents autonomes — applicable à nos API testing workflows
- [ ] **Signal faible** : Simon normalise les agents qui clonent, modifient, testent — quelle gouvernance pour les credentials de ces agents dans un contexte bancaire ?

---
## 📝 Notes personnelles

**Long-form bonus** : +0.5 (4671 chars, patterns détaillés avec code SQL)

**Lien avec le livre** : Ce cas illustre parfaitement le dilemme NHI — l'agent a besoin de :
- Credentials GitHub (read)
- Credentials pour écrire dans le repo tools
- Accès réseau (fetch Datasette instance)
- Aucune mention de rotation, scope limitation, audit trail

**Question architecturale** : Dans un contexte banque/finance, comment scoper les credentials d'un coding agent ? OAuth with limited scope ? Ephemeral tokens ? Audit chaque clone/commit ?

**Pattern réutilisable** :
```
1. Clone reference repo to /tmp (isolation)
2. Reference existing pattern (reduce description overhead)
3. Provide self-validation tool with --help documentation
```

Applicable à l'automatisation de tests API, génération de clients OAuth, etc.

---
## 📝 Opportunité éditoriale (score: 7/10)

**Thème** : Les coding agents ont déjà un problème de Non-Human Identity

**Angle** : Pendant qu'on débat de Zero Trust pour les humains, les agents IA clonent nos repos avec quels credentials ?

> 🪝 Hook : "Simon Willison vient de montrer un agent qui clone GitHub, modifie du code, et se teste tout seul. Personne n'a posé la question : avec quel token ?"

**Points clés** :
1. Les coding agents manipulent des credentials (GitHub, API keys) sans framework de gouvernance
2. Pattern émergent : agents auto-validants → surface d'attaque élargie
3. Banques/Assurances doivent anticiper : scope limitation, rotation, audit trail pour agent credentials

**Question ouverte** : Vos coding agents ont-ils des credentials à privilèges ? Qui les audite ?

**Angle contrarian** : Zero Trust pour humains, mais free-for-all pour agents — inversion du risque

**Hashtags** : #NonHumanIdentity #AgenticSecurity #ZeroTrust #APISecurity #DevSecOps
