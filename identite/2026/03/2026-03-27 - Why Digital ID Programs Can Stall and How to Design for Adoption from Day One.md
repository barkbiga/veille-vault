---
title: "Why Digital ID Programs Can Stall, and How to Design for Adoption from Day One"
date: 2026-03-27
source: "Spruce ID"
link: "https://blog.spruceid.com/digitalidentity-why-digital-id-programs-can-stall-and-how-to-design-for-adoption-from-day-one/"
categorie: "Identité"
action: "keep"
pertinence: 4.5
contrarian: false
vendor_bias: true
uid: "ab4921c53757"
tags:
  - digital-identity
  - mDL
  - adoption
  - ISO18013-5
  - W3C-VC
  - gouvernance
  - interoperabilité
  - standards
  - eIDAS
---

# Why Digital ID Programs Can Stall, and How to Design for Adoption from Day One

| | |
|---|---|
| **Pertinence** | 4.5/5 |
| **Catégorie** | Identité |
| **Source** | [Spruce ID Blog](https://blog.spruceid.com/digitalidentity-why-digital-id-programs-can-stall-and-how-to-design-for-adoption-from-day-one/) |

## Résumé

⚠️ **Contenu vendor** (SpruceID) mais analyse architecturale solide basée sur retours d'expérience réels des programmes mDL américains. Identifie 5 patterns d'échec prévisibles : friction d'enrollment > physique, lancement sans acceptation réelle, lock-in propriétaire, dépendance connectivité, absence de mandats agences. **Le framework "adoption-first design" est transposable aux wallets eIDAS 2.0 européens**. Insiste sur standards ouverts (ISO 18013-5, W3C VC) et offline-first (Bluetooth/NFC). Critique implicite : beaucoup d'États investissent millions pour des "demos" sans infrastructure d'acceptance.

## Actions recommandées

- [ ] **Audit eIDAS 2.0** : appliquer la grille des 5 failure modes aux specs wallets européens (enrollment UX, acceptance mandates, interop)
- [ ] **Architecture review** : vérifier capacités offline-first (ISO 18013-5) dans les ARF techniques ANSSI/eIDAS
- [ ] **Livre - Chapitre wallets** : intégrer "adoption gap as design problem" + cas US comme anti-patterns
- [ ] **LinkedIn editorial** : angle "Why Digital Identity Fails: 5 Predictable Patterns States Ignore" avec parallèle eIDAS 2.0
- [ ] **Due diligence vendors** : checker lock-in propriétaire vs open standards (W3C VC, ISO mDL) dans RFP wallet

---
## 📝 Opportunité éditoriale (score: 7/10)

**Thème** : Échec adoption identité numérique par design
**Angle** : Retex US mDL transposé à eIDAS 2.0 - les 5 pièges prévisibles

> 🪝 Hook : "Les États US ont investi des millions dans des mDL que personne n'utilise. L'Europe va-t-elle répéter les mêmes erreurs avec eIDAS 2.0 ?"

**Points clés** :
1. Adoption ≠ technologie qui marche, mais design de friction
2. Lancer sans acceptance = demo, pas infra
3. Lock-in propriétaire tue l'interop long terme
4. Offline-first = non négociable (ISO 18013-5)
5. Sans mandats agences, adoption volontaire stagne

**Question ouverte** : "Qui a audité l'UX d'enrollment des wallets ARF européens ? Quelqu'un a-t-il vérifié qu'ils seront acceptés dans les mairies françaises dès J+1 ?"

**Angle contrarian** : "Les specs techniques eIDAS 2.0 sont excellentes. Mais sans architecture d'acceptance et mandate enforcement, on aura des wallets conformes que personne n'utilisera."

**Hashtags** : #eIDAS2 #DigitalIdentity #mDL #IdentityWallet #OpenStandards #W3CVC #ISO18013

---
## 📝 Notes personnelles

**Applicable à :**
- Wallets eIDAS 2.0 (EUDIW, ARF national)
- CIAM onboarding (enrollment friction)
- API credential flows (offline capability design)

**Lien livre :**
- Ch. Agent Identity : les agents AI auront les mêmes pb d'acceptance (OAuth for agents = standard, mais qui l'accepte ?)

**Standards cités :**
- ISO/IEC 18013-5 : mDL avec offline via Bluetooth/NFC
- W3C Verifiable Credentials : format échange

**Anti-pattern key :**
"A verifiable digital credential that cannot be used is not infrastructure, it's a demonstration."

**Question architecture :**
Offline-first via ISO 18013-5 = BLE/NFC. Quid des APIs backend pour verification ? Hybrid model = présentation offline + log async ?
