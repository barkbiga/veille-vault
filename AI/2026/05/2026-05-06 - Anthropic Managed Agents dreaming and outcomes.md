---
title: "Anthropic will let its managed agents dream"
date: 2026-05-06
source: "The New Stack"
link: "https://thenewstack.io/anthropic-managed-agents-dreaming-outcomes/"
categorie: "AI"
action: "keep"
pertinence: 3.5
contrarian: false
vendor_bias: true
uid: "0a3d04466bc1"
tags:
  - AI-agents
  - Anthropic
  - agent-memory
  - agent-governance
  - self-improvement
  - multi-agent
---

# Anthropic Managed Agents dreaming and outcomes

| | |
|---|---|
| **Pertinence** | 3.5/5 |
| **Catégorie** | AI |
| **Source** | [The New Stack](https://thenewstack.io/anthropic-managed-agents-dreaming-outcomes/) |

⚠️ Contenu vendor (annonce produit Anthropic), mais implications gouvernance intéressantes.

## Résumé

Anthropic étend sa plateforme Managed Agents (beta publique avril 2026) avec 3 capacités : **(1) Dreaming** (research preview) — processus schedulé où Claude review ses sessions récentes, détecte patterns, met à jour sa mémoire (avec contrôle humain optionnel). Analogie : consolidation mémoire pendant sommeil humain. **(2) Outcomes** — définir critères de qualité pour une tâche, un agent "grader" séparé évalue la sortie (amélioration +10 points de succès vs prompting standard). Utile pour tâches subjectives (brand voice) ou exhaustives. **(3) Multi-agent orchestration** — agent lead qui décompose tâches et assigne à subagents, avec console pour voir steps. **Implication gouvernance** : agents qui s'auto-améliorent + écrivent leur propre mémoire + orchestrent d'autres agents = nouveaux défis d'audit, explicabilité, et accountability.

## Actions recommandées

- [ ] **Gouvernance self-improving agents** : définir policy pour review des modifications mémoire par dreaming (automatique vs human-in-loop)
- [ ] **Audit trail multi-agent** : si adoption orchestration, architecture de logging pour tracer décisions lead agent → subagents
- [ ] **Outcomes as policy** : explorer si "outcomes" peut servir de control framework pour agents (compliance checks as outcome criteria)
- [ ] **Risk assessment** : évaluer risque d'agents qui modifient leur propre mémoire sans supervision (drift, bias amplification)

---

## 📝 Notes personnelles

**Lien avec le livre** :
- Chapitre Agent Governance → section "Self-Improving Agents and Accountability Gap"
- Pattern dreaming = forme de "agent learning persistence" → qui contrôle cette mémoire ?

**Insights gouvernance** :
- **Dreaming avec contrôle humain** : Anthropic offre toggle automated vs human-review → good practice à documenter
- **Grader agent séparé** : pattern intéressant pour éviter "auto-grading" (contexte séparé → pas de triche)
- **Multi-agent audit** : Claude Console montre steps → mais sufficient pour compliance financière (DORA, PCI DSS) ?

**Questions architecturales** :
- **Mémoire agent as attack surface** : si agent écrit sa propre mémoire, peut-il être manipulé pour "oublier" des contraintes de sécurité ?
- **Outcomes vs policy-as-code** : outcomes = soft constraints (évaluation qualitative) vs hard constraints (validation technique) → complémentaires ?
- **Multi-agent identity** : lead agent qui spawn subagents → chaque subagent a son propre identity/credentials ou hérite du lead ?

**Vendor positioning** :
- Anthropic positionne Managed Agents comme "platform" (vs API-only de OpenAI) → veut capter ops/infra layer
- Features (dreaming, outcomes, orchestration) = différenciateurs vs concurrents (OpenAI Assistants, Google Vertex AI Agents)

**Signaux faibles** :
- "Dreaming" en research preview → terme marketing fort, mais capacité technique = scheduled memory consolidation
- +10 points success avec outcomes → chiffre non contextualisé (baseline ? tâches testées ?)
- Multi-agent orchestration devient standard feature (OpenAI Swarm, LangGraph, maintenant Anthropic)

**Pattern émergent** :
- Managed Agent platforms = nouvelle couche infra (comme managed Kubernetes)
- Control planes pour agents : console, audit trail, governance toggles → besoin exprimé par customers enterprise

**Connexion NHI** :
- Multi-agent orchestration = explosion credentials (1 lead + N subagents = 1+N identities à gérer)
- Mémoire agent persistée → où ? Qui y a accès ? Chiffrement ? Compliance data residency ?
