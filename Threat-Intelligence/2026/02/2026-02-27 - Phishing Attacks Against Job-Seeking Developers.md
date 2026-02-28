---
title: "Phishing Attacks Against People Seeking Programming Jobs"
date: 2026-02-27
source: "Schneier on Security"
link: "https://www.schneier.com/blog/archives/2026/02/phishing-attacks-against-people-seeking-programming-jobs.html"
categorie: "Threat-Intelligence"
action: "keep"
pertinence: 3.5
contrarian: false
vendor_bias: false
uid: "3cb0ad96ec30"
tags:
  - phishing
  - social-engineering
  - supply-chain
  - north-korea
  - malware
  - developer-security
  - code-execution
---

# Phishing Attacks Against People Seeking Programming Jobs

| | |
|---|---|
| **Pertinence** | 3.5/5 |
| **Catégorie** | Threat-Intelligence |
| **Source** | [Schneier on Security](https://www.schneier.com/blog/archives/2026/02/phishing-attacks-against-people-seeking-programming-jobs.html) |

## Résumé

Acteurs nord-coréens se font passer pour recruteurs tech et envoient des "coding challenges" aux candidats. Quand les développeurs exécutent le code fourni (pour le tester/modifier), il installe du malware. Technique de social engineering ciblant spécifiquement les devs, exploitant le réflexe naturel d'exécuter du code lors d'un entretien technique. Commentaire pertinent dans l'article : ce n'est pas nouveau en soi (bad actors font ça depuis des années), mais l'angle "recruiter + coding challenge" est une évolution tactique. Un commentateur suggère un contre-pattern intéressant : légitimes entreprises pourraient inclure des pièges "do not run this code" pour filtrer les candidats imprudents.

## Actions recommandées

- [ ] Documenter ce pattern comme supply chain attack indirect (compromission via job candidates, puis pivot vers corporate network si exécuté sur work machine)
- [ ] Évaluer les politiques de sandboxing pour coding challenges dans les processus de recrutement
- [ ] Analyser les implications pour la formation des développeurs : "never run untrusted code" est-il encore enseigné ?
- [ ] Examiner si nos propres processus de recrutement tech pourraient être exploités de cette manière

---
## 📝 Notes personnelles

**Social engineering évolutif** : L'angle "recruiter + coding challenge" est brillant parce qu'il exploite deux vecteurs :
1. La pression psychologique d'un entretien (le candidat veut bien faire)
2. Le réflexe professionnel du dev (exécuter du code pour le comprendre/tester)

**Supply chain angle** : Le commentaire "in hopes someone will run it on their work machine" est la vraie menace. Un candidat qui teste le challenge sur son laptop perso = impact limité. Un candidat qui le fait sur sa machine de travail (parce qu'il a les tools déjà configurés) = initial access dans le corporate network.

**Pattern de défense** : Le commentaire de Matt est astucieux : "Include comments that say 'Do not run this code as-is or you fail'". C'est un test de sécurité déguisé en coding challenge. Les bons candidats lisent le code avant de l'exécuter. Mais est-ce réaliste ? Combien de devs lisent ligne par ligne un challenge de 500 lignes avant de le run ?

**Évolution tactique** : North Korea est connu pour ses campagnes ciblant les devs (lazarus group, etc.). Ce pattern est une évolution naturelle : plutôt que de compromettre des dépôts publics (supply chain classique), ils compromettent des individus pendant le recrutement.

**Connexion agentic workflows** : Avec la montée des agents AI qui génèrent/exécutent du code automatiquement, ce type d'attaque pourrait devenir plus efficace. Un agent pourrait-il être trompé par un "coding challenge" malveillant ? Probablement, si le challenge ressemble à du code légitime.

**Pertinence modérée (3.5/5)** : Intéressant comme évolution tactique et pour le supply chain angle, mais pas directement lié aux thèmes core (Zero Trust, API Security, IAM). Cependant, le destinataire embauche peut-être des devs et devrait être conscient de cette menace.

**Questions ouvertes** :
- Comment les entreprises peuvent-elles sécuriser leurs processus de recrutement tech ?
- Devrait-on fournir des sandboxes dédiées pour les coding challenges ?
- Les plateformes de coding challenge en ligne (HackerRank, LeetCode, etc.) sont-elles la solution ?
