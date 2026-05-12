---
title: "Your AI Use Is Breaking My Brain - The Zombie Internet"
date: 2026-05-12
source: "Simon Willison"
link: "https://simonwillison.net/2026/May/11/zombie-internet/"
categorie: "Trends"
action: "keep"
pertinence: 3.0
contrarian: false
vendor_bias: false
uid: "b7e3c9d4f1a6"
tags:
  - zombie-internet
  - ai-ethics
  - trust
  - content-authenticity
  - signal-faible
  - dead-internet-theory
---

# Your AI Use Is Breaking My Brain - The Zombie Internet

| | |
|---|---|
| **Pertinence** | 3/5 |
| **Catégorie** | Trends |
| **Source** | [Simon Willison](https://simonwillison.net/2026/May/11/zombie-internet/) |

## Résumé

Simon Willison partage un article externe (Cory Doctorow style) sur la **dégradation de la confiance dans les contenus web** causée par la prolifération de contenus générés par IA. Concept : **"Zombie Internet"** — un web où il devient impossible de distinguer humain vs. machine, signal vs. bruit. **Impact sur la sécurité** : si les utilisateurs ne peuvent plus faire confiance aux contenus, ils deviennent vulnérables aux attaques de phishing/social engineering sophistiquées (emails IA-generated indétectables). **Signal faible** : la course aux content authenticity solutions (C2PA, watermarking, cryptographic provenance) indique que la confiance devient un problème architectural, pas juste éditorial. **Lien avec agent identity** : si on ne peut pas prouver qu'un contenu vient d'un humain (ou d'un agent légitime), comment construire des systèmes de confiance ? Challenge indirect l'axiome #4 "L'identité est le nouveau périmètre" → il faut prouver cryptographiquement l'identité du créateur de contenu, pas juste de l'accédant.

## Actions recommandées

- [ ] **Surveiller les initiatives C2PA** (Content Authenticity Initiative) : standard de provenance cryptographique pour contenus
- [ ] **Évaluer les use cases internes** : où la provenance du contenu est critique ? (compliance docs, audit reports, customer communications)
- [ ] **Prototyper du content signing** : signer cryptographiquement les documents sensibles (reports, policies) pour prouver l'authorship
- [ ] **Auditer les emails sortants** : distinguer emails humains vs. générés par IA (ex: chatbots support). Transparence nécessaire ?
- [ ] **Former les équipes** : sensibilisation au phishing IA-enhanced (deepfakes vocaux, emails hyper-personnalisés)
- [ ] **Challenger les systèmes d'authentification** : est-ce qu'identifier l'utilisateur suffit, ou faut-il aussi identifier le "mode" (humain vs. agent assisté) ?

---

## 📝 Notes personnelles

**Zombie Internet** :
- Origine : "Dead Internet Theory" (théorie complotiste que le web est dominé par des bots)
- Version 2026 : pas complotiste, c'est une réalité — contenus IA sont indiscernables des humains
- Conséquence : érosion de la confiance, repli sur des communautés fermées/vérifiées

**Lien avec la sécurité** :
- **Phishing IA-enhanced** : emails générés par LLM, parfaitement rédigés, contextuellement pertinents
- **Deepfakes** : appels vocaux imitant le CEO, demandant un virement urgent (déjà observé)
- **Social engineering** : agents IA capables de mener des conversations longues pour gagner la confiance

**Content Authenticity Initiative (C2PA)** :
- Standard Adobe/Microsoft/BBC pour signer cryptographiquement les contenus (images, vidéos, textes)
- Métadonnées : qui a créé, quand, avec quels outils, modifications successives
- Challenge : adoption faible, interop limitée, facilement contournable (strip metadata)

**Lien avec agent identity** :
- Si un agent IA génère un document, il devrait signer avec son identité (credential)
- Transparence : "Ce rapport a été généré par Agent_Compliance_v2, supervisé par Alice (risk_manager)"
- Auditabilité : tracer la chaîne de création (humain → prompt → agent → output → validation humaine)

**Questions ouvertes** :
- **Législation** : obligation de labelliser les contenus IA ? (EU AI Act mentionne la transparence)
- **Faux positifs** : un humain aidé par Grammarly = contenu humain ou IA ?
- **Provenance cryptographique** : qui contrôle les clés de signature ? Centralisé (CA) ou décentralisé (blockchain) ?

**Signal faible** :
- La confiance devient un problème **architectural**, pas juste social
- Solutions émergentes : cryptographic provenance, identity-bound content, verifiable authorship
- Convergence avec Zero Trust : "never trust, always verify" s'applique maintenant aux contenus, pas juste aux accès

**Contrarian potential** :
- Pas vraiment contrarian, c'est du discours critique mainstream sur l'IA
- Mais pourrait challenger l'optimisme sur "l'IA rend productif" → oui, mais au prix de la confiance globale

**Action éditoriale** :
- Trop philosophique pour un post LinkedIn technique
- Mais pourrait être un **thread** : "La confiance est le nouveau périmètre : pourquoi les contenus IA nécessitent une provenance cryptographique"

