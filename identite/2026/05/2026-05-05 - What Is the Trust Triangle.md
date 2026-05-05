---
title: "What Is the Trust Triangle, and Why Does It Matter for Digital Identity?"
date: 2026-05-05
source: "Spruce ID"
link: "https://blog.spruceid.com/what-is-the-trust-triangle-and-why-does-it-matter-for-digital-identity/"
categorie: "Identité"
action: "keep"
pertinence: 4
contrarian: false
vendor_bias: true
uid: "9fc9352678e3"
tags:
  - Verifiable-Credentials
  - Digital-Identity
  - Trust-Architecture
  - Selective-Disclosure
  - Privacy-By-Design
  - eIDAS
---

# What Is the Trust Triangle, and Why Does It Matter for Digital Identity?

| | |
|---|---|
| **Pertinence** | 4/5 |
| **Catégorie** | IAM / Architecture |
| **Source** | [Spruce ID Blog](https://blog.spruceid.com/what-is-the-trust-triangle-and-why-does-it-matter-for-digital-identity/) |

## Résumé

⚠️ **Contenu vendor (Spruce ID)** — Analyse architecturale du "trust triangle" (issuer-holder-verifier), modèle fondamental des systèmes de credentials vérifiables. La clé : dans les systèmes legacy, le verifier contacte l'issuer à chaque vérification (créant tracking + dépendance). Dans le trust triangle, **la credential signée devient la source de confiance** — le verifier vérifie la signature cryptographique sans callback à l'issuer. Cela déplace le contrôle vers le holder, qui décide quand/où présenter, et rend possible la **selective disclosure** (prouver "âge >21" sans révéler la date de naissance exacte). C'est un choix architectural avec implications privacy by design : qui contrôle les données, qui trace les usages, qui a l'accountability.

## Actions recommandées

- [ ] **Évaluation eIDAS 2.0** : vérifier que les wallets européens implémentent bien le trust triangle (pas de callback issuer)
- [ ] **Selective disclosure** : documenter les protocoles (BBS+, CL signatures) et leurs trade-offs performance/privacy
- [ ] **Threat model** : analyser les attaques spécifiques au trust triangle (holder credential reuse, issuer key compromise, verifier collusion)
- [ ] **API implications** : comment OAuth 2.0/OIDC s'articule avec verifiable credentials? (SIOP, VP token?)
- [ ] **Benchmark** : comparer trust triangle vs federated identity (SAML/OIDC) sur critères privacy/performance/resilience

---

## 📝 Opportunité éditoriale (score: 6/10)

**Thème** : Architecture is Policy — comment la structure technique encode les choix de privacy

**Angle** : Le trust triangle n'est pas juste un diagramme, c'est un manifeste politique déguisé en architecture.

> 🪝 **Hook** : "Deux systèmes d'identité. L'un trace chaque vérification. L'autre n'en trace aucune. La différence ? Trois lignes dans un diagramme."

**Points clés** :
1. Dans les systèmes legacy, l'issuer sait **chaque fois** que vous utilisez votre credential (tracking by design)
2. Dans le trust triangle, l'issuer signe **une fois**, puis perd la visibilité (privacy by design)
3. Selective disclosure : montrer "je suis majeur" sans révéler "je suis né le X"

**Question ouverte** : Si l'Europe force les wallets eIDAS 2.0 à implémenter le trust triangle, pendant que les BigTech restent sur OAuth centralisé, crée-t-on deux internets de l'identité incompatibles?

**Angle contrarian** : (pas vraiment contrarian, plutôt explicatif)

**Hashtags** : #DigitalIdentity #eIDAS2 #VerifiableCredentials #PrivacyByDesign #ZeroKnowledge

---

## Architecture et trade-offs

### Trust Triangle vs Federated Identity

| | **Trust Triangle** | **Federated (OIDC)** |
|---|---|---|
| **Dépendance issuer** | Aucune après émission | Callback à chaque authz |
| **Tracking issuer** | Impossible | Complet |
| **Offline verification** | Possible | Impossible |
| **Révocation** | Complexe (status list) | Simple (invalidation token) |
| **Selective disclosure** | Natif | Difficile/impossible |

**Le trade-off central** :
- **Privacy** ↑ : Holder control, pas de tracking, selective disclosure
- **Révocation** ↓ : Si credential compromise, difficile de la révoquer instantanément (status lists publiées périodiquement, pas real-time)

### Schéma du Trust Triangle

```
        Issuer
       /      \
    signs    (no callback!)
     /          \
Holder -----> Verifier
     presents + verifies signature
```

**Comparé au modèle legacy** :
```
        Issuer
       /  |   \
    signs |  callback
     /    |     \
Holder -----> Verifier
     presents
```

La flèche `callback` du verifier vers l'issuer = tracking point.

## Selective Disclosure : Exemples

**Cas d'usage** : Prouver l'âge (>21) sans révéler la date de naissance

**Techniques crypto** :
- **Zero-Knowledge Proofs** (e.g., zk-SNARKs) : mathématiquement prouver une propriété sans révéler les données
- **BBS+ Signatures** : signer plusieurs attributs, holder peut révéler N sur M attributs
- **CL Signatures** (Camenisch-Lysyanskaya) : utilisé dans Hyperledger Indy

**Trade-off** : Plus de privacy = plus de complexité crypto = moins de performance

## Liens avec réglementations

### eIDAS 2.0 (EU Digital Identity Wallet)
- **Article 6a** : Le wallet doit permettre le "selective disclosure" 
- Implémentation trust triangle probable (pas de callback centralisé aux issuers gouvernementaux)
- Révocation : status lists publiées par issuers, vérifiées par verifiers

### FAPI (Financial-grade API)
- Actuellement basé sur OAuth 2.0 (modèle federated, avec callback AS)
- Évolution possible : FAPI + Verifiable Credentials (hybrid model?)
- Question ouverte : comment gérer selective disclosure dans open banking?

## Questions ouvertes

1. **Révocation en temps réel** : Comment concilier trust triangle (pas de callback) et révocation instantanée (credential compromise)?
2. **Holder liability** : Si le holder contrôle la présentation, est-il responsable d'un usage frauduleux? (legal implications)
3. **Verifier collusion** : Si 10 verifiers partagent leurs logs, peuvent-ils reconstituer le tracking holder? (privacy attack)
4. **Interop OAuth/VC** : OAuth DPoP + Verifiable Credentials = solution hybrid pour APIs? (Self-Issued OP?)

---

## 📝 Notes personnelles

**Architecture = policy** : La phrase "the trust triangle defines how trust itself is structured" est fondamentale. Ce n'est pas un choix technique neutre, c'est un choix politique (qui a le pouvoir de surveiller).

**Lien NHI** : Les agents IA sont des "non-human holders". Peuvent-ils gérer des verifiable credentials? Qui décide de leur "présentation"? Le owner de l'agent? L'agent lui-même (autonomous holder)? 🤯

**Contrarian potential** : Et si le trust triangle était incompatible avec la compliance financière? Les banques *doivent* tracer les transactions. Le "pas de callback issuer" = perte d'audit trail. DORA vs Privacy?

**Next steps** : Lire la spec W3C Verifiable Credentials Data Model 2.0 + regarder l'implémentation eIDAS 2.0 wallet (public?).

