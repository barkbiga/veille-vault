---
title: "Why Liveness Checks and Facial Matching Are Not the Same Thing, and Why the Difference Matters"
date: 2026-04-22
source: "Spruce ID"
link: "https://blog.spruceid.com/digitalidentity-why-liveness-checks-and-facial-matching-are-not-the-same-thing-and-why-the-difference-matters/"
categorie: "IAM / Identité Numérique"
action: "keep"
pertinence: 4.0
contrarian: false
vendor_bias: true
uid: "55a134ff342d"
tags:
  - Identity-Proofing
  - NIST
  - IAL
  - Biometrics
  - Data-Minimization
  - Privacy-by-Design
  - Government-ID
  - eIDAS
---

# Why Liveness Checks and Facial Matching Are Not the Same Thing

| | |
|---|---|
| **Pertinence** | 4/5 |
| **Catégorie** | IAM / Identité Numérique |
| **Source** | [Spruce ID](https://blog.spruceid.com/digitalidentity-why-liveness-checks-and-facial-matching-are-not-the-same-thing-and-why-the-difference-matters/) |

## Résumé

⚠️ **Contenu vendor** — Clarification conceptuelle essentielle pour les législateurs et architectes identity proofing : **liveness detection** (confirme présence humaine réelle, pas deepfake) ≠ **facial matching** (compare visage live vs. photo ID stockée). Implications privacy radicalement différentes : liveness peut être on-device et éphémère (data minimization), facial matching requiert retention d'image de référence (risque gouvernance). NIST IAL2 permet facial matching mais ne l'impose pas ; IAL1 le rend optionnel. **Risque policy** : confondre les deux → mandats disproportionnés ou gaps de sécurité (facial matching sans liveness = spoofing vulnerability).

## Actions recommandées

- [ ] Auditer les RFPs bancaires/assurance : vérifient-elles que les vendors séparent liveness (on-device) et facial matching (server-side) ?
- [ ] Challenger les implémentations CIAM : le facial matching est-il IAL2-justifié ou sur-engineering pour des use cases IAL1 ?
- [ ] Documenter pattern "liveness on-device + facial matching server-side encrypted with retention <24h" comme best practice privacy-preserving
- [ ] Vérifier compliance eIDAS 2.0 wallet : liveness detection obligatoire, facial matching optionnel ?
- [ ] Intégrer dans formations DSI : "biometric verification" = terme flou, toujours décomposer en liveness vs. matching

---

## 📝 Notes personnelles

**Définitions précises** :
- **Liveness detection** : Répond à "Is there a real, live person right now?" (anti-spoofing). Méthodes : blink, head turn, analyse micro-mouvements. **N'identifie pas** la personne.
- **Facial matching** : Répond à "Does face on camera = face on stored ID?". Génère confidence score de match. **Identifie** la personne.

**NIST Identity Assurance Levels (IAL)** :
- **IAL1** : Flexible proofing, biometric matching optionnel
- **IAL2** : Stronger confidence, facial matching = UNE méthode possible (pas la seule). Alternatives : non-biometric, digital evidence.
- **Liveness** à IAL2 : Rôle support essentiel pour protéger le facial matching (sinon risque replay attack photo/vidéo)

**Privacy implications** :
- **Liveness** :
  - Peut tourner on-device (calcul local)
  - Données usage liveness → discardées immédiatement (ephemeral)
  - Minimise transmission/retention
  - **Data minimization compliant**
  
- **Facial matching** :
  - Requiert accès à reference image (DL, passport)
  - Image stockée → où ? combien de temps ? par qui ?
  - Server-side matching → vendor voit biometric data
  - Questions gouvernance : retention policy, secondary use, contractual controls
  - **Privacy-preserving possible** : encryption, strict retention limits, enforceable contracts

**Risques policy** :
1. **Mandat disproportionné** : Imposer facial matching à IAL1 (low-risk services) → over-collection
2. **Gap sécurité** : Facial matching sans liveness → spoofing trivial (photo printed)
3. **Confusion vendor evaluation** : "Do you do biometric verification?" → réponse floue, ne distingue pas liveness vs. matching

**Architecture recommandée** (privacy-preserving) :
```
User device:
  └─ Liveness check (on-device, ephemeral)
       ↓ (si pass)
  └─ Capture live image
       ↓ (encrypted)
Server (vendor or gov):
  └─ Facial matching (encrypted image vs. encrypted reference)
  └─ Retention < 24h
  └─ Contractual: no secondary use, no training dataset
```

**Questions ouvertes** :
- **eIDAS 2.0 wallet** : Liveness obligatoire pour Level of Assurance High ? Facial matching optionnel ou requis ?
- **FAPI/SCA** : Strong Customer Authentication (PSD3/DSP3) pourrait-il utiliser liveness sans facial matching (juste prouver présence humaine, pas identité) ?
- **Vendor lock-in** : Si facial matching server-side, quelle portabilité des reference images entre providers ?
- **False rejection rate** : Liveness on-device vs. server-side → taux FRR différents ? Impact UX ?

**Lien banking/assurance** :
- Onboarding client banque : IAL2 justifié (AML/KYC)
- Mais auth récurrente : liveness seul suffit (pas besoin re-match à chaque login)
- **Pattern** : Facial matching à l'enrollment, liveness aux re-auth
- DSP3 Level 2 SCA : biometric local (liveness implicite) ≠ biometric remote (matching nécessaire ?)

**Vendor bias** :
- Spruce ID = vendor de solutions identity (wallets, credentials)
- Angle article = éduquer acheteurs/législateurs (pas pushy sales)
- Mais motivation sous-jacente : positionner Spruce comme privacy-first (vs. Onfido, Jumio, etc.)
- **Impact scoring** : -0.5 pour vendor bias, mais contenu technique solide

**Data minimization principle** :
- Article cite principe GDPR-adjacent : collecter only what's necessary for defined purpose
- Liveness = necessary pour anti-spoofing
- Facial matching = necessary pour identity proofing, mais pas pour toute interaction
- **Implication architecturale** : Séparer enrollment (high assurance, matching OK) vs. authentication (lower friction, liveness suffit)

**Long-form bonus** : 7350 chars, framework structuré NIST, exemples gouvernance → +0.5

**Pertinence finale** : 4.0 (4 base - 0.5 vendor bias + 0.5 long-form)
- Pertinent pour DSI finance (onboarding, KYC, remote identity)
- Educational pour éviter confusion liveness/matching dans specs
- Pas directement API security mais IAM foundational
