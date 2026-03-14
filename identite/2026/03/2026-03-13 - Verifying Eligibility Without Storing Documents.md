---
title: "Verifying Eligibility Without Storing Documents"
date: 2026-03-13
source: "Spruce ID"
link: "https://blog.spruceid.com/zerotrust-verifying-eligibility-without-storing-documents/"
categorie: "Identité"
action: "keep"
pertinence: 4.5
contrarian: false
vendor_bias: true
uid: "e75d999b5dd4"
tags:
  - ZeroTrust
  - VerifiableCredentials
  - DataMinimization
  - SelectiveDisclosure
  - PrivacyByDesign
  - CIAM
---

# Verifying Eligibility Without Storing Documents

| | |
|---|---|
| **Pertinence** | 4.5/5 |
| **Catégorie** | Identité |
| **Source** | [Spruce ID](https://blog.spruceid.com/zerotrust-verifying-eligibility-without-storing-documents/) |

## Résumé

⚠️ **Contenu vendor** — Spruce ID présente une approche Zero Trust pour la vérification d'éligibilité basée sur les verifiable credentials. Au lieu de collecter et stocker des documents (permis, justificatifs de domicile), les systèmes vérifient cryptographiquement des claims spécifiques tout en laissant les données sous contrôle utilisateur. **Selective disclosure** (ex: prouver +21 ans sans révéler la date de naissance exacte) + data minimization = réduction drastique de la surface d'attaque. Architecture alignée avec le principe ZT "store less sensitive data". Article long-form (6500 chars) avec framework conceptuel clair, mais reste orienté vers la promotion de l'écosystème Spruce.

## Actions recommandées

- [ ] Évaluer l'applicabilité des verifiable credentials pour les parcours KYC/onboarding bancaire (vs. stockage actuel de pièces d'identité)
- [ ] Challenger l'architecture actuelle : quels claims minimaux suffisent pour chaque use case ? (résidence, majorité, éligibilité crédit)
- [ ] Intégrer la selective disclosure dans le chapitre NHI du livre : analogie avec les scopes OAuth minimaux pour agents
- [ ] Benchmarker les standards W3C VC vs. OpenID4VC pour interopérabilité européenne (eIDAS 2.0 wallet)

---

## 📝 Opportunité éditoriale (score: 7/10)

**Thème** : Zero Trust Identity — Vérifier sans collecter
**Angle** : Remettre en question le réflexe "upload de document" dans les parcours numériques

> 🪝 Hook : "Chaque vérification KYC commence par un upload de pièce d'identité. Mais si la question est 'êtes-vous majeur et résident en France', pourquoi stocker adresse complète, photo, et numéro de permis pendant 5 ans ?"

**Points clés** :
1. Document-based verification = over-collection structurelle (surface d'attaque inutile)
2. Verifiable credentials + selective disclosure = vérification cryptographique sans stockage
3. Alignement naturel avec Zero Trust : "store less" > "store securely"

**Question ouverte** : Les banques françaises sont-elles prêtes à abandonner le stockage de documents au profit de la vérification de claims tiers (ANSSI, ANTS, DGFIP) ?

**Angle contrarian** : "Le coffre-fort numérique n'est pas la solution — c'est encore du stockage centralisé. La vraie innovation, c'est de ne rien stocker du tout."

**Hashtags** : #ZeroTrust #VerifiableCredentials #DataMinimization #eIDAS #PrivacyByDesign #CIAM

---

## 📝 Notes personnelles

**Architecture clé** :
- Émetteurs de confiance (DMV, universités, gouv) → credentials signées numériquement
- Vérification = signature check (pas de revue manuelle)
- Selective disclosure = prouver un fact sans révéler le document complet

**Lien avec AXIOME #1 (Zero Trust)** :
Renforce : ZT assume breaches → minimiser les données stockées = meilleure stratégie que sécuriser un data lake de documents scannés.

**Angle NHI** :
Transposable aux agents IA : prouver qu'un agent a l'autorisation d'accéder à une ressource sans révéler son scope complet ou ses credentials upstream. Selective disclosure = principe des capability tokens (GNAP, OAuth Token Exchange).

**Standards à suivre** :
- W3C Verifiable Credentials Data Model
- OpenID4VC (OpenID for Verifiable Credentials)
- ISO/IEC 18013-5 (mDL - mobile Driver's License)
- eIDAS 2.0 (EU Digital Identity Wallet)

**Risques vendor lock-in** :
Spruce ID pousse son stack (DIDKit, Credible, Kepler). Vérifier interopérabilité avec Wallet européen et autres implémentations (MATTR, Ping Identity, Microsoft Entra Verified ID).
