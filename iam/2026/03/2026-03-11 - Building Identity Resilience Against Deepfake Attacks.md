---
title: "Building Identity Resilience Against Deepfake Attacks"
date: 2026-03-11
source: "BankInfoSecurity"
link: "https://www.bankinfosecurity.com/building-identity-resilience-against-deepfake-attacks-a-30964"
categorie: "IAM"
action: keep
pertinence: 4.0
contrarian: true
vendor_bias: false
uid: "https://www.bankinfosecurity.com/building-identity-resilience-against-deepfake-attacks-a-30964"
tags:
  - deepfake
  - identity
  - resilience
  - IAM
  - CIAM
  - impersonation
---

# Building Identity Resilience Against Deepfake Attacks

| | |
|---|---|
| **Pertinence** | 4/5 |
| **Catégorie** | IAM |
| **Source** | [BankInfoSecurity](https://www.bankinfosecurity.com/building-identity-resilience-against-deepfake-attacks-a-30964) |

## Résumé
🔄 CONTRARIAN — Gartner (Apeksha Kaushik) remet en cause l'axiome "l'identité est le nouveau périmètre" en soulignant que la détection seule est insuffisante face aux deepfakes : l'identité elle-même devient un vecteur d'attaque, non un rempart. La posture de résilience identitaire dépasse donc la simple détection biométrique ou documentaire. Les organisations doivent adopter des défenses en couches combinant détection, prévention et signaux de risque contextuels larges. Ce cadre interroge directement la solidité des flux OIDC/FAPI basés sur la vérification d'identité initiale (enrollment) dans les secteurs banque et santé. L'article positionne la continuité de la confiance (ongoing trust) comme priorité sur la confiance ponctuelle à l'authentification.

## Actions recommandées
- [ ] Réviser les flux d'enrollment CIAM pour intégrer des signaux de risque continus post-authentification (liveness detection, behavioral analytics)
- [ ] Challenger les hypothèses d'identité forte dans les architectures Zero Trust : un token FAPI ne garantit pas l'absence d'usurpation deepfake en amont
- [ ] Intégrer des contrôles de détection deepfake au niveau des API d'onboarding (KYC/AML) dans les contextes bancaires et santé
- [ ] Évaluer les solutions de continuous identity verification comme signal complémentaire aux Authorization Servers

---
## 📝 Notes personnelles
