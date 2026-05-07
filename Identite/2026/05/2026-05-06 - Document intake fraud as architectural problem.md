---
title: "Why Document Intake Is a Fraud Vector, and How Modern Systems Can Close It"
date: 2026-05-06
source: "Spruce ID"
link: "https://blog.spruceid.com/why-document-intake-is-a-fraud-vector-and-how-modern-systems-can-close-it/"
categorie: "Identité"
action: "keep"
pertinence: 3.5
contrarian: true
vendor_bias: true
uid: "fb3fb5c322e9"
tags:
  - identity-proofing
  - fraud
  - system-design
  - government
  - verification
  - eIDAS
---

# Document intake fraud as architectural problem

| | |
|---|---|
| **Pertinence** | 3.5/5 |
| **Catégorie** | Identité |
| **Source** | [Spruce ID](https://blog.spruceid.com/why-document-intake-is-a-fraud-vector-and-how-modern-systems-can-close-it/) |

🔄 **CONTRARIAN** — La fraude documentaire n'est pas un problème de "bad actors" mais de design système. L'article challenge l'approche classique "former les reviewers" en montrant que la variabilité humaine sous pression est structurelle, pas corrigible par training.

⚠️ Contenu vendor (Spruce ID propose solutions), mais l'analyse des patterns de fraude est solide et transposable.

## Résumé

Spruce ID analyse la fraude aux programmes gouvernementaux (benefits, licenses) comme un problème d'architecture système, pas de comportement criminel. **Insight clé** : les processus manuels de vérification documentaire créent de l'inconsistance *by design* — reviewers sous pression, standards qui dérivent entre équipes, outils limités. La fraude exploite cette inconsistance prévisible. **4 patterns identifiés** : (1) Document forgery (outils design grand public = facilité de falsification), (2) Identity substitution (doc réel, mauvaise personne), (3) Document reuse (même doc pour multiple programmes ou recycled après expiration), (4) Manufactured identity (docs techniquement valides car identité volée upstream). **Solutions architecturales** : vérification automatisée (format specs, security features, metadata), identity proofing (match live image vs doc), unique identifier par doc (détection duplicatas cross-program), checks upstream identity validity.

## Actions recommandées

- [ ] **Transposition bancaire** : analyser si nos processus KYC/onboarding ont des patterns similaires d'inconsistance structurelle
- [ ] **Identity proofing** : évaluer liveness detection + biometric matching pour clients (eIDAS 2.0, PSD3)
- [ ] **Document fingerprinting** : POC pour unique identifier par doc soumis (détection reuse multi-applications)
- [ ] **Automated checks** : intégrer verification de metadata/security features documents (vs pure visual review)

---

## 📝 Opportunité éditoriale (score: 6/10)

**Thème** : La fraude documentaire est un bug de design, pas un crime imprévisible
**Angle** : Ce que les programmes gouvernementaux nous apprennent sur le KYC bancaire

> 🪝 Hook : "On forme les reviewers KYC à détecter les faux docs. Mais si le vrai problème, c'était qu'on leur demande de faire un travail impossible ?"

**Points clés** :
1. Variabilité humaine sous pression = inconsistance structurelle que la fraude exploite
2. 4 patterns prévisibles : forgery, substitution, reuse, manufactured identity
3. Solutions = architecture (automated checks, identity proofing, unique doc IDs), pas training
4. Analogie : manual review = code sans tests → ça marche "en général" mais fail sur edge cases

**Question ouverte** : "Vos processus KYC sont-ils conçus pour qu'un reviewer sous pression fasse toujours le bon choix, ou pour qu'il n'ait pas à le faire ?"

**Hashtags** : #IdentityProofing #KYC #FraudPrevention #eIDAS #SystemDesign #DigitalIdentity

---

## 📝 Notes personnelles

**AXIOME CHALLENGÉ** :
"L'identité est le nouveau périmètre de sécurité" → Oui, mais l'article montre que nos processus d'identité reposent encore sur jugement humain variable, pas sur architecture robuste. Le "périmètre" est poreux by design.

**Lien avec le livre** :
- Chapitre Identity Proofing → section sur limits of manual processes
- Connexion eIDAS 2.0 : European Digital Identity Wallets pourraient court-circuiter document intake (verifiable credentials)

**Insights architecturaux** :
- **Fraud as system failure** : framework mental puissant → shift de "bad actors" à "bad design"
- **Automated checks ≠ AI magic** : checks simples (format specs, metadata) mais appliqués systématiquement > AI sophistiquée appliquée inconsistamment
- **Unique document IDs** : pattern simple mais puissant pour détecter reuse (transposable aux APIs → request IDs pour détecter replay attacks)

**Transposition secteur bancaire** :
- **KYC onboarding** : même vulnérabilités (manual review, pression volumes, variabilité entre analystes)
- **Document reuse** : client qui soumet même justificatif domicile à 3 banques différentes (légitime ou fraude ?)
- **Identity substitution** : selfie + doc d'identité → liveness detection crucial (PSD2 SCA, eIDAS LoA High)

**Questions non résolues** :
- **Trade-off friction vs security** : automated checks = plus de rejets légitimes ? Impact UX ?
- **Cost** : infrastructure de vérification automatisée (metadata, security features) → investissement significatif
- **Cross-border** : comment vérifier metadata/security features de docs étrangers (variété formats) ?

**Vendor bias** :
- Spruce ID vend des solutions d'identity proofing → l'article pitch subtilement automated systems
- Mais l'analyse des 4 patterns est objective et bien sourcée (pas de metrics fantaisistes)

**Connexion réglementaire** :
- **eIDAS 2.0** : European Digital Identity Wallets = alternative architecturale (verifiable credentials > document intake)
- **DORA** : operational resilience → processus manuels = risk (inconsistency, human error)
- **PSD3 (upcoming)** : strong customer authentication → liveness + biometric matching deviendra standard
