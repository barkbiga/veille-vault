---
title: "Fragments February 23 - Running High-Permissioned Agents Safely (OpenClaw)"
date: 2026-02-23
source: "Martin Fowler"
link: "https://martinfowler.com/fragments/2026-02-23.html"
categorie: "Architecture"
action: keep
pertinence: 4.0
contrarian: false
vendor_bias: false
uid: "https://martinfowler.com/fragments/2026-02-23.html"
tags:
  - ai-agents
  - non-human-identity
  - blast-radius
  - zero-trust
  - sandbox
  - security-patterns
---

# Fragments February 23 - Running High-Permissioned Agents Safely (OpenClaw)

| | |
|---|---|
| **Pertinence** | 4/5 |
| **Catégorie** | Architecture |
| **Source** | [Martin Fowler](https://martinfowler.com/fragments/2026-02-23.html) |

## Résumé
Jim Gumbley (Thoughtworks) adresse directement la question des agents à haute permission (high-permissioned agents) — le cas OpenClaw — en reconnaissant qu'**il n'existe pas de méthode prouvée sûre aujourd'hui** pour les opérer. L'approche recommandée est résolument orientée réduction du blast radius plutôt que prévention absolue : isolation via cloud VMs ou micro-VMs locales (Gondolin). C'est un signal fort pour les architectes sécurité API : la posture Zero Trust traditionnelle (authenticate → authorize → audit) est nécessaire mais insuffisante pour les agents autonomes à haute permission. Le principe de moindre privilège doit être complété par une isolation d'exécution au niveau infrastructure. Pertinent pour secteurs banque/santé où les agents commencent à opérer sur des APIs critiques (paiement, dossiers patients).

## Actions recommandées
- [ ] Évaluer l'isolation d'exécution des agents NHI en production : les agents tournent-ils dans des environnements sandboxés ou directement sur infra partagée ?
- [ ] Tester Gondolin ou équivalent micro-VM pour les agents expérimentaux avant promotion en production
- [ ] Définir une classification "permission level" pour les agents (low/medium/high-permissioned) et des contrôles proportionnels
- [ ] Réviser les scopes OAuth accordés aux agents : appliquer le principe de moindre privilège dynamique (token downscoping par tâche)
- [ ] Lire l'article Thoughtworks source : https://www.thoughtworks.com/insights/blog/security/want-run-openclaw

---
## 📝 Notes personnelles
