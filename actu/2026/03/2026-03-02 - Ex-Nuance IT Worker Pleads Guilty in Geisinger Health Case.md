---
title: "Ex-Nuance IT Worker Pleads Guilty in Geisinger Health Case"
date: 2026-03-02
source: "BankInfoSecurity"
link: "https://www.bankinfosecurity.com/ex-nuance-worker-pleads-guilty-in-geisinger-health-case-a-30893"
categorie: "actu"
action: keep
pertinence: 3.0
contrarian: false
vendor_bias: false
uid: "https://www.bankinfosecurity.com/ex-nuance-worker-pleads-guilty-in-geisinger-health-case-a-30893"
tags:
  - insider-threat
  - IAM
  - NHI
  - santé
  - offboarding
  - zero-trust
---

# Ex-Nuance IT Worker Pleads Guilty in Geisinger Health Case

| | |
|---|---|
| **Pertinence** | 3/5 |
| **Catégorie** | Actu |
| **Source** | [BankInfoSecurity](https://www.bankinfosecurity.com/ex-nuance-worker-pleads-guilty-in-geisinger-health-case-a-30893) |

## Résumé
Un ex-employé IT de Nuance Communications a téléchargé 1,2 million de dossiers patients de Geisinger Health deux jours après son licenciement en 2023, stockés sur un disque personnel. Le cas illustre une défaillance critique du processus d'offboarding : accès non révoqué post-terminaison. Cas d'école pour les architectes IAM : le provisioning/déprovisioning est un vecteur majeur, y compris pour les comptes de service (NHI) qui survivent aux départs humains.

## Actions recommandées
- [ ] Auditer les processus d'offboarding pour inclure la révocation immédiate des tokens, credentials et accès API (humains ET non-humains)
- [ ] Implémenter des alertes sur les volumes de téléchargement anormaux post-notification RH via des contrôles Zero Trust contextuels
- [ ] Vérifier que les comptes de service associés à des employés licenciés sont également désactivés

---
## 📝 Notes personnelles
