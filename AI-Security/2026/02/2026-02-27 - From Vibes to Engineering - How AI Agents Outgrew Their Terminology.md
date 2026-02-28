---
title: "From vibes to engineering: How AI agents outgrew their own terminology"
date: 2026-02-27
source: "The New Stack"
link: "https://thenewstack.io/vibe-coding-agentic-engineering/"
categorie: "AI-Security"
action: "keep"
pertinence: 4.5
contrarian: false
vendor_bias: false
uid: "3b28c18b41ac"
tags:
  - agentic-workflows
  - ai-agents
  - software-engineering
  - NHI
  - agent-identity
  - terminology
  - DevOps
  - orchestration
---

# From vibes to engineering: How AI agents outgrew their own terminology

| | |
|---|---|
| **Pertinence** | 4.5/5 |
| **Catégorie** | AI-Security |
| **Source** | [The New Stack](https://thenewstack.io/vibe-coding-agentic-engineering/) |

## Résumé

Karpathy propose de remplacer "vibe coding" par "agentic engineering" — non pas par caprice sémantique, mais parce que la pratique a changé. "Vibe coding" (itération rapide, intuitive, sans structure profonde) fonctionne pour les prototypes mais s'effondre à l'échelle. Les agents modernes (step-change des 1-2 derniers mois) peuvent compléter des tâches complexes, mais uniquement avec des guardrails stricts : documentation, tests complets, discipline structurelle. Sans cela, "les agents génèrent de la dette technique à vitesse machine". L'orchestration d'agents nécessite une rigueur d'ingénierie, pas moins. La production de code ne correspond plus à la capacité de l'absorber. Forrester avait prédit ce shift 14 mois avant Karpathy.

## Actions recommandées

- [ ] Intégrer le concept d'"agentic engineering" dans le chapitre NHI du livre — les agents nécessitent une discipline d'orchestration similaire à la gestion de service accounts
- [ ] Documenter les parallèles entre orchestration d'agents et IAM pour NHI : les agents ont-ils besoin de credentials, scopes, policies formelles ?
- [ ] Analyser les "guardrails" mentionnés (documentation, tests) comme équivalents de security policies pour agents autonomes
- [ ] Évaluer les implications pour la gouvernance : qui est responsable quand un agent génère du code ? Accountability model ?

---
## 📝 Notes personnelles

**Step-change récent** : David Mytton (Arcjet) note une "huge step change in agent coding capabilities in the last 1-2 months". Les agents passent de "nécessite plusieurs itérations humaines" à "capable de compléter des tâches complexes". Ce changement de phase est crucial pour le contexte NHI — les agents deviennent de véritables acteurs autonomes, pas juste des assistants.

**Discipline vs chaos** : Le passage de "vibe" à "engineering" capture un besoin de structure. Citation clé de Mayank Agarwal (Resolve AI) : "The speed to produce code doesn't match the speed to productively absorb it, and without proper engineering practices, agentic workflows just generate tech debt at machine speed."

**Analogie avec NHI** : Les agents sont dans la même position que les service accounts il y a 10 ans : nécessaires, puissants, mais sans framework de gouvernance mature. L'article note qu'il faut "clear guardrails" — documentation, tests que l'agent peut exécuter. N'est-ce pas l'équivalent de policies/scopes pour API keys ?

**Orchestration > génération** : "You're not writing code directly, you're orchestrating agents" — cette formulation est capitale. L'orchestration implique délégation, supervision, coordination. Cela nécessite une identité pour chaque agent, des permissions, des audit logs. On entre dans le domaine IAM.

**Forrester prediction** : Diego Lo Giudice avait prédit fin 2024 que "vibe coding will transform into vibe engineering by the end of 2026". Il avait raison 14 mois à l'avance. Sa dimension "skills" est intéressante : "only those who know about software engineering can really succeed with [vibe engineering]". Les agents amplifient les compétences, ne les remplacent pas.

**Connexion au livre** : Ce shift terminologique capture un moment de maturation. Les agents ne sont plus des gadgets — ils deviennent des citoyens de première classe dans l'infrastructure. Cela renforce l'urgence du chapitre NHI : si les agents génèrent du code en production, ils ont besoin d'une identité formelle, de credentials, de gouvernance.

**Question ouverte** : Quand un agent a accès au repo, au CI/CD, aux secrets — comment le distingue-t-on d'un service account ? Comment audit-on ses actions ? Qui est liable si l'agent introduit une vulnérabilité ?

---
## 📝 Opportunité éditoriale (score: 8/10)

**Thème** : Les agents AI sont les nouveaux service accounts — et on a oublié de leur donner une identité
**Angle** : Le passage de "vibe coding" à "agentic engineering" n'est pas sémantique, c'est un signal que les agents sont devenus des acteurs autonomes. Et comme pour les service accounts, on découvre qu'ils ont besoin de gouvernance, credentials, policies.

> 🪝 Hook : "Karpathy vient de renommer 'vibe coding' en 'agentic engineering'. Vous pensez que c'est un débat de mots ? C'est en réalité l'admission que nous orchestrons désormais des agents autonomes — et qu'on ne leur a toujours pas donné d'identité formelle."

**Points clés** :
1. Les agents modernes (step-change des 1-2 derniers mois) peuvent compléter des tâches complexes de manière autonome
2. Sans "guardrails" (docs, tests, structure), ils génèrent de la dette technique à vitesse machine
3. L'orchestration d'agents = délégation, supervision, coordination → nécessite IAM
4. Analogie avec les service accounts il y a 10 ans : nécessaires, puissants, mais sans framework de gouvernance
5. Questions ouvertes : credentials ? scopes ? audit logs ? qui est responsible quand un agent casse quelque chose ?

**Question ouverte** : Si vous orchestrez des agents qui commitent du code en production, ne sont-ils pas déjà des Non-Human Identities ? Et si oui, où sont leurs credentials management, leur RBAC, leurs audit trails ?

**Angle contrarian** : L'industrie est en train de réinventer les erreurs des service accounts (credentials en clair, over-privileged, aucun audit) pour les agents AI. On appelle ça "agentic engineering" mais on oublie le "governance engineering".

**Hashtags** : #AgenticAI #NHI #NonHumanIdentity #IAM #Security #SoftwareEngineering #DevOps #AgentOrchestration
