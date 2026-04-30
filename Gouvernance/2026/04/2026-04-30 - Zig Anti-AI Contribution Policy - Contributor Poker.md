---
title: "The Zig project's rationale for their firm anti-AI contribution policy"
date: 2026-04-30
source: "Simon Willison"
link: "https://simonwillison.net/2026/Apr/30/zig-anti-ai/#atom-everything"
categorie: "Gouvernance"
action: "borderline"
pertinence: 3.5
contrarian: true
vendor_bias: false
uid: "d2b58487a8b6"
tags:
  - Open-Source
  - AI-Policy
  - Governance
  - Contributor-Management
  - LLM-Ban
  - Trust-Building
---

# The Zig project's rationale for their firm anti-AI contribution policy

| | |
|---|---|
| **Pertinence** | 3.5/5 |
| **Catégorie** | Gouvernance |
| **Source** | [Simon Willison](https://simonwillison.net/2026/Apr/30/zig-anti-ai/#atom-everything) |

## Résumé

🔄 **CONTRARIAN** — Zig (langage système) a une politique anti-LLM absolue : interdiction totale pour issues, PRs, commentaires. **Rationale de Loris Cro** (VP Community) : les projets open source réussis investissent dans les *contributeurs*, pas dans les *contributions*. Chaque PR est un pari sur l'humain ("contributor poker") — le temps passé en review sert à créer des contributeurs de confiance long-terme. **LLM casse ce modèle** : une PR parfaite générée par IA ne construit aucune relation, aucun trust, aucune capacité future. **Conséquence inattendue** : Bun (runtime JS acquis par Anthropic, développé en Zig) a forké Zig et ne peut pas upstreamer ses optimisations 4x performance car générées avec LLM.

## Actions recommandées

- [ ] Analyser le parallèle avec la gouvernance API/IAM : investit-on dans les *intégrateurs* ou dans les *intégrations* ?
- [ ] Challenger pour le livre : les agents IA cassent-ils le modèle de confiance progressive (OAuth incremental consent, token refresh) ?
- [ ] Étudier "contributor poker" comme pattern pour onboarding développeurs dans écosystèmes API complexes (banking)
- [ ] Évaluer : si un agent génère un appel API parfait, pourquoi un humain devrait-il le reviewer au lieu de régénérer ?

---
## 📝 Opportunité éditoriale (score: 8/10)

**Thème** : La gouvernance est un pari sur les humains, pas sur le code
**Angle** : Pourquoi Zig refuse tout code généré par IA — et ce que ça révèle sur la confiance dans les systèmes critiques

> 🪝 Hook : Zig a banni toute contribution générée par IA. Pas par technophobie — mais parce qu'ils investissent dans les contributeurs, pas dans les contributions. Et ça change tout.

**Points clés** :
1. Les projets open source réussis jouent au "contributor poker" — ils parient sur l'humain, pas sur sa première PR
2. Une PR générée par LLM peut être parfaite — mais elle ne construit aucune confiance, aucune relation, aucune capacité future
3. Bun (acquis par Anthropic !) ne peut pas upstreamer ses optimisations 4x car générées par IA
4. La vraie question : "Si l'IA génère un code parfait, pourquoi un mainteneur devrait-il le reviewer au lieu de le régénérer ?"

**Question ouverte** : Les systèmes critiques (banking, santé) devraient-ils adopter la même politique — investir dans les développeurs qui *comprennent* l'architecture, plutôt que dans du code "correct" mais opaque ?

**Angle contrarian** : L'IA ne remplacera pas les développeurs — mais elle détruit les mécanismes de construction de confiance qui rendent les équipes efficaces.

**Hashtags** : #OpenSource #AIGovernance #TrustByDesign #CriticalSystems #ZeroTrust

---
## 📝 Notes personnelles

**Angle CONTRARIAN fort** : Challenge l'axiome implicite "l'automatisation est toujours mieux". Zig dit NON — et ils ont des arguments solides.

**Analogie banking** : Les systèmes bancaires critiques suivent le même modèle. On n'embauche pas pour "livrer du code" mais pour "comprendre le système et transmettre". Les agents IA cassent ce modèle.

**Lien Zero Trust** : La confiance se construit progressivement (least privilege, incremental consent). Une PR LLM parfaite court-circuite ce processus — c'est un **trust maximalism**, pas du Zero Trust.

**Paradoxe Bun/Anthropic** : Anthropic a acquis Bun (développé en Zig) et utilise massivement l'IA pour le développer... mais ne peut plus contribuer upstream. Fragmentation inévitable ?

**Question pour le livre NHI** : Les agents IA doivent-ils suivre le même modèle de "trust progressif" que les humains ? Ou faut-il un modèle radicalement différent ?

**Signal faible** : Si Zig (systèmes critiques) bannit l'IA et que ça *fonctionne*, ça valide un modèle alternatif pour les secteurs régulés (banking, santé). À suivre.
