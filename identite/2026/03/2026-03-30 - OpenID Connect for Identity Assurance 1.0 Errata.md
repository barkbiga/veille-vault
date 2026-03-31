---
title: "Public Review Period for Errata to OpenID Connect for Identity Assurance 1.0"
date: 2026-03-30
source: "OpenID Foundation"
link: "https://openid.net/public-review-period-for-errata-to-openid-connect-for-identity-assurance-1-0/"
categorie: "Identité"
action: "keep"
pertinence: 3.5
contrarian: false
vendor_bias: false
uid: "d0d20d8d2a3d"
tags:
  - OpenID
  - OIDC
  - Identity-Assurance
  - eKYC
  - Standards
  - CIAM
  - Banking
---

# Public Review Period for Errata to OpenID Connect for Identity Assurance 1.0

| | |
|---|---|
| **Pertinence** | 3.5/5 |
| **Catégorie** | Identité |
| **Source** | [OpenID Foundation](https://openid.net/public-review-period-for-errata-to-openid-connect-for-identity-assurance-1-0/) |

## Résumé

L'OpenID Foundation lance la période de review publique (45 jours, jusqu'au 14 mai 2026) pour le premier ensemble d'errata de la spécification **OpenID Connect for Identity Assurance 1.0**. Cette spec, finalisée précédemment, est cruciale pour l'eKYC et les use cases bancaires nécessitant des niveaux d'assurance d'identité vérifiables via OIDC. Les corrections seront soumises à un vote des membres après la review. Important pour les implémentations CIAM en contexte réglementé (banque, assurance).

## Actions recommandées

- [ ] Suivre le lien vers les errata (https://openid.net/specs/openid-connect-4-identity-assurance-1_0-17.html) pour identifier les changements vs la version finale
- [ ] Évaluer l'impact des corrections sur les implémentations OIDC existantes en production (notamment flows eKYC/onboarding digital)
- [ ] Participer à la review si votre architecture s'appuie sur Identity Assurance (rejoindre le WG eKYC & IDA)
- [ ] Intégrer dans la roadmap CIAM : alignement avec eIDAS 2.0 et DSP3 pour open banking européen

---
## 📝 Notes personnelles

Contexte : OpenID Connect for Identity Assurance étend OIDC avec des claims structurées pour transmettre des données d'identité vérifiées (documents, niveaux d'assurance, etc.). Critique pour la conformité DSP3/PSD2 et les parcours KYC digitaux.

Pertinence modérée (3.5/5) car c'est un errata (corrections mineures), pas une nouvelle version majeure. Mais à surveiller : toute divergence entre implémentations et spec peut créer des problèmes d'interopérabilité dans les fédérations d'identité bancaires.

Lien avec axiome #2 (FAPI) : Identity Assurance est souvent couplé avec FAPI pour créer des flows haute sécurité + haute assurance (ex: strong customer authentication + verified identity).
