---
title: "What Does 'Offline-Capable' Mean When it Comes to Verifiable Digital Credentials?"
date: 2026-04-28
source: "Spruce ID"
link: "https://blog.spruceid.com/what-does-offline-capable-mean-when-it-comes-to-verifiable-digital-credentials/"
categorie: "Identité Numérique"
action: "keep"
pertinence: 3.5
contrarian: false
vendor_bias: true
uid: "d0f78f4a9d3e"
tags:
  - Digital-Identity
  - PKI
  - W3C-VC
  - ISO-18013-5
  - Offline-Verification
  - mDL
  - NFC
  - Revocation
---

# What Does "Offline-Capable" Mean When it Comes to Verifiable Digital Credentials?

| | |
|---|---|
| **Pertinence** | 3.5/5 |
| **Catégorie** | Identité Numérique |
| **Source** | [Spruce ID](https://blog.spruceid.com/what-does-offline-capable-mean-when-it-comes-to-verifiable-digital-credentials/) |

## Résumé

⚠️ **Contenu vendor (Spruce ID)** — Clarification technique du concept "offline-capable" pour les verifiable credentials. **Définition stricte** : capacité du vérifieur à confirer authenticité + intégrité d'une credential SANS connexion réseau au moment de la présentation. Repose sur 3 piliers : (1) **Signatures cryptographiques vérifiées localement** via PKI (public key pré-chargée), (2) **Présentation device-to-device** via NFC/QR code (pas de serveur intermédiaire), (3) **Statut de révocation sans réseau** via embedded status (expiration, tokens courts) ou pre-downloaded revocation lists. Standards : ISO 18013-5 (mDL) + W3C Verifiable Credentials. Cas d'usage : disaster response, zones rurales, sites mobiles d'urgence.

## Actions recommandées

- [ ] Croiser avec eIDAS 2.0 (European Digital Identity Wallet) — offline capability requis ?
- [ ] Valider le pattern de révocation pour les certificats OAuth/FAPI (CRL vs OCSP vs embedded)
- [ ] Intégrer l'analogie PKI offline comme référence pour expliquer Zero Trust "assume breach"
- [ ] Documenter le trade-off latence/fraîcheur pour les revocation lists (acceptable en disaster, pas pour banking)
- [ ] Étudier si les FIDO2/WebAuthn credentials sont "offline-capable" au sens strict

---
## 📝 Notes personnelles

**Architecture offline-first** :
- Public key pré-distribuée (trust anchor local)
- Signature voyage avec la credential
- Vérification = validation crypto locale

→ C'est le modèle **X.509 classique**, appliqué aux verifiable credentials mobiles.

**Révocation = talon d'Achille** :
- Embedded status (expiration) : simple, mais freshness limitée
- Pre-downloaded lists : scalable, mais pas real-time
- Pas de solution parfaite sans réseau

**Use cases gouvernementaux** :
- Disaster response (réseaux down)
- Rural (connectivité faible)
- Mobile sites (événements, urgences)

→ Très éloigné des cas bancaires (connectivité assumée, real-time fraud detection requis).

**Lien Zero Trust** : l'offline-capable force à pré-distribuer la trust — contradiction apparente avec "never trust, always verify" qui assume connectivity. **Subtilité** : "verify" reste, mais le trust anchor est établi offline.

**W3C VC + ISO 18013-5** : convergence standards identity, mais adoption bancaire = 0 pour l'instant.

---
## 📝 Notes personnelles (suite)

**Challenger AXIOME 4** ("L'identité est le nouveau périmètre") :
→ Si le périmètre dépend d'une connexion temps réel pour vérifier l'identité (CRL, OCSP), alors l'identité n'est PAS le périmètre, c'est la connectivité qui l'est.

Offline-capable credentials = vrai Zero Trust périmètre-less, car la vérification est locale.

**Question pour le livre** : Les APIs bancaires FAPI peuvent-elles fonctionner offline ? Non. Donc la métaphore "identité = périmètre" tient uniquement si on assume connectivity = constante. C'est une faiblesse architecturale déguisée en feature.
