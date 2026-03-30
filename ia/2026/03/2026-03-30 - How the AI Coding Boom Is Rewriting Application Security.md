---
title: "How the AI Coding Boom Is Rewriting Application Security"
date: 2026-03-30
source: "BankInfoSecurity"
link: "https://www.bankinfosecurity.com/how-ai-coding-boom-rewriting-application-security-a-31265"
categorie: "IA"
action: keep
pertinence: 3.5
contrarian: false
vendor_bias: false
uid: "https://www.bankinfosecurity.com/how-ai-coding-boom-rewriting-application-security-a-31265"
tags:
  - IA
  - appsec
  - SAST
  - DAST
  - AI-generated-code
  - runtime-defense
  - architecture
---

# How the AI Coding Boom Is Rewriting Application Security

| | |
|---|---|
| **Pertinence** | 3.5/5 |
| **Catégorie** | IA |
| **Source** | [BankInfoSecurity](https://www.bankinfosecurity.com/how-ai-coding-boom-rewriting-application-security-a-31265) |

## Résumé
John Cowgill (Costanoa Ventures) analyse le passage de l'analyse statique (SAST) vers la défense runtime dans un monde où le code AI-généré arrive plus vite que les équipes sécurité peuvent le reviewer. Le point clé est le déplacement du risque du niveau ligne-de-code vers le niveau système — les vulnérabilités ne sont plus individuelles mais architecturales. Pour les services financiers régulés, cela soulève la question de la responsabilité sur le code produit par des assistants IA dans les équipes de développement bancaire ou assurance. Pertinent pour le livre : les agents IA qui génèrent du code introduisent des identités non-humaines dans la chaîne de livraison logicielle.

## Actions recommandées
- [ ] Évaluer comment DORA article 16 (testing) s'applique au code AI-généré dans les SI financiers
- [ ] Intégrer la dimension "code AI-généré" dans le chapitre sur la surface d'attaque des agents IA (livre)
- [ ] Chercher des retex sur les pipelines CI/CD avec scanners adaptatifs pour code LLM

---
## Notes personnelles
📐 PATTERN SHIFT — Le shift de SAST vers runtime defense est un signal architectural fort. Connexion avec le livre : les agents qui génèrent du code sont eux-mêmes des NHI, et leur output code crée de nouveaux NHI (service accounts, API keys hardcodées).
↔️ AppSec → Banque/Assurance — Les équipes DevSecOps des SI régulés vont devoir traiter le code AI-généré comme une surface de risque spécifique sous DORA.
