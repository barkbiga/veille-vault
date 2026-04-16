---
title: "How Do Verifiable Digital Credentials Actually Work? A Non-Technical Explanation"
date: 2026-04-16
source: "Spruce ID"
link: "https://blog.spruceid.com/digitalidentity-how-do-verifiable-digital-credentials-actually-work-a-non-technical-explanation/"
categorie: "Identité"
action: "keep"
pertinence: 4.5
contrarian: false
vendor_bias: true
uid: "ec5a7f29c566"
tags:
  - VerifiableCredentials
  - eIDAS2
  - DigitalWallet
  - SelectiveDisclosure
  - EUDI
  - IAM
---

# How Do Verifiable Digital Credentials Actually Work? A Non-Technical Explanation

| | |
|---|---|
| **Pertinence** | 4.5/5 |
| **Catégorie** | Identité |
| **Source** | [Spruce ID](https://blog.spruceid.com/digitalidentity-how-do-verifiable-digital-credentials-actually-work-a-non-technical-explanation/) |

## Résumé

⚠️ **Contenu vendor** — Spruce ID (fournisseur de solutions VCs) propose une explication pédagogique solide du fonctionnement des credentials vérifiables. Utilise l'analogie du notaire pour expliquer le modèle issuer-holder-verifier. Point clé : la vérification est **cryptographiquement autonome** (pas d'appel réseau à l'issuer), et le holder contrôle la divulgation sélective. Pertinent pour eIDAS 2.0 et EUDI Wallet, mais reste orienté évangélisation du modèle VC.

## Actions recommandées

- [ ] Intégrer cette pédagogie dans le chapitre livre sur l'identité décentralisée vs. fédérée
- [ ] Mapper ce modèle sur les exigences eIDAS 2.0 : quelles tensions entre sélective disclosure et traçabilité réglementaire ?
- [ ] Challenger : ce modèle tient-il face aux exigences DORA/NIS2 de traçabilité et d'audit centralisé ?
- [ ] Analyser l'impact sur les Authorization Servers : qui devient le Policy Decision Point si le holder contrôle la divulgation ?

---
## 📝 Notes personnelles

### Architecture du modèle 3-party

1. **Issuer** : signe cryptographiquement le credential à l'émission (ex: DMV, université, agence publique). Une fois signé, l'issuer n'est plus dans la boucle de vérification.

2. **Holder** : stocke le credential dans un wallet mobile. Contrôle **ce qui est partagé et quand** via selective disclosure (ex : prouver l'âge sans révéler la date de naissance exacte).

3. **Verifier** : vérifie la signature de l'issuer **localement**, sans appeler l'issuer. Répond à deux questions : (a) issuer de confiance ? (b) credential non altéré ?

### Différence clé avec l'identité fédérée classique

- **Fédération (OAuth/OIDC)** : le verifier (RP) demande au holder de s'authentifier chez l'issuer (IdP) à chaque transaction → **online check**.
- **VCs** : le holder présente un credential **pré-signé**, vérifiable **offline** → pas de back-channel avec l'issuer.

### Analogie du notaire

Credential ≈ lettre notariée. La signature notariale permet à quiconque de vérifier l'authenticité **sans rappeler le notaire**. Différence : la signature est cryptographique (non forgeable), pas physique.

### Selective Disclosure

Le credential peut être structuré pour que **chaque champ soit indépendamment vérifiable**. La signature globale tient même si seul un sous-ensemble des données est présenté. Exemples :
- Vérification d'âge → pas besoin de l'adresse
- Preuve de résidence → pas besoin de la date de naissance

**Implication pour les APIs** : si le holder peut filtrer les claims avant présentation, comment gérer les scopes OAuth qui spécifient des ensembles d'attributs ? Qui arbitre les conflits entre la policy du verifier et les préférences du holder ?

### Questions architecturales ouvertes

1. **Révocation** : comment un issuer révoque un credential déjà distribué si le modèle est "offline-first" ? L'article ne traite pas ce point (probablement via status list ou bitstring, mais cela réintroduit un appel réseau).

2. **Traçabilité** : eIDAS 2.0 impose des logs d'usage. Si le holder présente un VC directement au verifier, où est le point d'audit centralisé ? ANSSI acceptera-t-il un modèle où l'émetteur ne voit pas les usages ?

3. **Liaison avec OAuth** : comment intégrer les VCs dans un flow OAuth classique ? Draft IETF `oauth-selective-disclosure-jwt` ? Ou remplacer le `/userinfo` par une présentation VC ?

4. **Trust framework** : qui maintient la liste des issuers de confiance ? Dans eIDAS 2.0, c'est la Trusted List. Dans un modèle décentralisé pur, c'est plus flou.

### Bias vendor à noter

Spruce ID construit des produits autour des VCs (wallets, issuer tooling). L'article est pédagogique mais **n'aborde pas les limitations** :
- Complexité de déploiement (QES, HSM, key management pour les issuers)
- UX wallet (perte de clés = perte d'identité ?)
- Interopérabilité : SD-JWT vs. JSON-LD BBS+ vs. mDL ISO 18013-5

---
## 📝 Opportunité éditoriale (score: 7/10)

**Thème** : Identité décentralisée vs. fédérée — le grand malentendu

**Angle** : Les VCs ne sont PAS une évolution d'OAuth. Ce sont deux modèles architecturaux incompatibles, et prétendre les "intégrer" crée des incohérences de gouvernance.

> 🪝 Hook : *"L'Europe impose les wallets eIDAS 2.0. Mais personne ne vous dit que ce modèle casse le principal avantage d'OAuth : la révocation centralisée."*

**Points clés** :
1. OAuth = **online federation**, l'IdP reste dans la boucle → révocation temps réel, audit centralisé
2. VCs = **offline credentials**, l'issuer sort de la boucle après émission → holder autonome, mais révocation complexe
3. Selective disclosure = transfert de la policy decision du verifier vers le holder → qui décide vraiment des scopes ?

**Question ouverte** : 
*Si le holder contrôle la divulgation sélective, comment un API gateway applique-t-il une policy de sécurité uniforme ? Faut-il re-centraliser la gouvernance via des Verifiable Presentations standardisées ?*

**Angle contrarian** :
Les VCs sont vendus comme "privacy by design", mais en finance réglementée (DORA, LCB-FT), l'absence de traçabilité centralisée est un bug, pas une feature. **L'identité décentralisée est-elle un luxe de la tech, incompatible avec les secteurs régulés ?**

**Hashtags** : #eIDAS2 #VerifiableCredentials #OAuth #DigitalIdentity #ZeroTrust #APIGovernance #SelectiveDisclosure