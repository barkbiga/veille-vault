---
title: "Quoting James Shore on AI Maintenance Costs"
date: 2026-05-12
source: "Simon Willison (quoting James Shore)"
link: "https://simonwillison.net/2026/May/11/james-shore/"
categorie: "Engineering"
action: "keep"
pertinence: 5.0
contrarian: true
vendor_bias: false
uid: "d2f8e7a3b9c4"
tags:
  - ai-productivity
  - maintenance-costs
  - technical-debt
  - contrarian
  - tco
  - code-quality
  - long-term-thinking
---

# Quoting James Shore on AI Maintenance Costs

| | |
|---|---|
| **Pertinence** | 5/5 |
| **Catégorie** | Engineering |
| **Source** | [Simon Willison (quoting James Shore)](https://simonwillison.net/2026/May/11/james-shore/) |

## Résumé

🔄 **CONTRARIAN MAJEUR** — James Shore (expert XP/TDD) démonte l'argument "l'IA booste la productivité des développeurs". **Thèse centrale** : **90% du coût du logiciel est dans la maintenance, pas l'écriture initiale**. L'IA peut accélérer l'écriture de code, mais si ce code est de qualité inférieure (moins lisible, moins testé, architecture bancale), le coût de maintenance explose. Quote clé : *"If AI-generated code increases maintenance costs by just 10%, it wipes out all the productivity gains from faster writing."* **Angle financier** : les entreprises célèbrent des gains de vélocité à court terme (features shipped faster) sans mesurer l'impact à long terme (bugs, refactoring, dette technique). **Lien avec la sécurité** : code de mauvaise qualité = plus de vulnérabilités. Les outils SAST/DAST détectent les bugs évidents, pas les failles architecturales (injection, broken access control, insecure deserialization). **Directement actionnable** : challenger les métriques de productivité IA dans les organisations.

## Actions recommandées

- [ ] **Mesurer la qualité du code IA-généré** : coverage de tests, complexité cyclomatique, code smells (SonarQube), findings SAST
- [ ] **Définir un baseline de maintenance costs** : temps passé en debugging, refactoring, hotfixes sur code legacy vs. IA-generated
- [ ] **Auditer les features IA-generated** : taux de bugs en production, délai moyen de résolution, nombre de rollbacks
- [ ] **Implémenter des guardrails qualité** : code review obligatoire (humain) pour tout code IA, seuil minimal de test coverage (ex: 80%)
- [ ] **Former les équipes** : sensibilisation à la dette technique, cost of ownership vs. time-to-market
- [ ] **Challenger les business cases IA** : exiger une projection TCO (Total Cost of Ownership) sur 3 ans, pas juste une vélocité initiale
- [ ] **Documenter les incidents** : tracer les bugs/vulnérabilités introduits par code IA vs. code humain (data-driven decision)

---

## 📝 Opportunité éditoriale (score: 9/10)

**Thème** : L'IA booste la vélocité, mais explose les coûts de maintenance  
**Angle** : Contrarian + données financières (90% coût = maintenance)

> 🪝 Hook : "Votre équipe dev code 2x plus vite avec l'IA ? Super. Mais 90% du coût du logiciel est dans la maintenance. Si le code IA-généré est 10% plus difficile à maintenir, vous perdez de l'argent. Voici pourquoi personne ne mesure ça."

**Points clés** :
1. **Illusion de la productivité** : vélocité ≠ valeur long terme
2. **90/10 rule** : 90% du coût est maintenance/évolution, 10% écriture initiale
3. **Code quality matters** : lisibilité, testabilité, architecture > vitesse d'écriture
4. **Sécurité** : code de mauvaise qualité = plus de vulnérabilités (broken access control, injection)
5. **Mesure** : personne ne track le TCO du code IA-généré (coût de maintenance, bugs, refactoring)

**Question ouverte** : "Votre organisation mesure-t-elle la qualité du code IA-généré ? Avez-vous des métriques de maintenance costs avant/après adoption de l'IA ?"

**Angle contrarian** : "Contrairement au discours ambiant, je pense que l'IA générative va *augmenter* les coûts logiciels à long terme. Les gains de vélocité sont réels, mais les coûts de maintenance cachés sont sous-estimés."

**Hashtags** : #AIProductivity #TechnicalDebt #CodeQuality #TCO #SoftwareEngineering #Maintenance

---

## 📝 Notes personnelles

**La thèse de James Shore** :
- Basée sur des décennies d'expérience en XP (Extreme Programming), TDD (Test-Driven Development)
- Référence probable : études classiques sur le coût du logiciel (Fred Brooks, "The Mythical Man-Month")
- 90/10 rule = observation empirique : la majorité du coût est post-écriture (debugging, évolution, maintenance)

**Pourquoi le code IA peut augmenter les coûts de maintenance** :
1. **Qualité variable** : l'IA génère du code qui "marche" mais n'est pas forcément idiomatique, lisible, ou maintenable
2. **Manque de tests** : l'IA génère rarement des tests complets (edge cases, error handling)
3. **Architecture bancale** : l'IA optimise pour le local (la fonction), pas le global (l'architecture)
4. **Tribal knowledge manquant** : le code IA n'a pas de "pourquoi". Quand il faut le modifier, personne ne sait pourquoi c'était fait comme ça.
5. **Copilot effect** : les devs acceptent les suggestions sans comprendre, créent des dépendances fragiles

**Lien avec la sécurité** :
- **Vulnérabilités architecturales** : broken access control (manque de vérification des permissions), insecure deserialization (trust user input)
- **Injection** : SQL, NoSQL, command injection si l'IA ne sanitise pas les inputs
- **Secrets hardcodés** : l'IA peut suggérer du code avec API keys en dur (GitHub Copilot l'a fait)
- **Dependencies** : l'IA peut importer des packages vulnérables sans vérifier (supply chain risk)

**Exemple chiffré hypothétique** :
- Sans IA : 10 jours pour écrire une feature, 90 jours de maintenance sur 3 ans = 100 jours total
- Avec IA : 5 jours pour écrire, mais maintenance +10% (99 jours) = 104 jours total → **PERTE nette**
- Si maintenance +20% → 113 jours → perte de 13%

**Contrarian sur quel axiome ?** :
- Pas directement lié aux 5 axiomes du destinataire
- Mais challenge un axiome implicite du marché : "IA = ROI positif garanti"
- Plus précisément : "La vélocité est la bonne métrique de productivité dev"

**Ce qui manque dans le discours mainstream** :
- **Métriques de qualité** : cyclomatic complexity, test coverage, code churn
- **Coût réel de la dette technique** : combien coûte un refactoring complet d'une codebase IA-generated ?
- **Comparaison longitudinale** : bugs/vulnerabilities rate dans du code IA vs. humain sur 1-3 ans

**Questions ouvertes** :
- Existe-t-il des études empiriques sur le maintenance cost du code IA-généré ? (Probablement trop tôt, l'IA générative est récente)
- Les outils SAST/DAST détectent-ils plus de vulnérabilités dans du code IA ? (À surveiller)
- Les équipes qui utilisent massivement l'IA ont-elles un taux de turnover plus élevé ? (Frustration de maintenir du code incompréhensible)

**Sources à surveiller** :
- Articles académiques sur code quality metrics (ICSE, FSE conferences)
- Rapports d'incidents : CVEs attribuables à du code IA-généré
- Retex d'entreprises (GitHub, Google, Meta) sur l'impact long terme du code IA

**Action pour le destinataire** :
- Intégrer cette thèse dans le livre : "Chapter: The Hidden Costs of AI-Generated Code"
- Proposer un framework de mesure : TCO = (time_to_write × hourly_rate) + (maintenance_time × hourly_rate) + (bug_cost × incident_rate)

