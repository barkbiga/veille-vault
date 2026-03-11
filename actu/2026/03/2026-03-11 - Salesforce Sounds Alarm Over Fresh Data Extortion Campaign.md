---
title: "Salesforce Sounds Alarm Over Fresh Data Extortion Campaign"
date: 2026-03-11
source: "BankInfoSecurity"
link: "https://www.bankinfosecurity.com/salesforce-sounds-alarm-over-fresh-data-extortion-campaign-a-30958"
categorie: "actu"
action: borderline
pertinence: 2.5
contrarian: false
vendor_bias: false
uid: "https://www.bankinfosecurity.com/salesforce-sounds-alarm-over-fresh-data-extortion-campaign-a-30958"
tags:
  - misconfiguration
  - data-exfiltration
  - SaaS-security
  - guest-accounts
  - CRM
---

# Salesforce Sounds Alarm Over Fresh Data Extortion Campaign

| | |
|---|---|
| **Pertinence** | 2.5/5 |
| **Catégorie** | Actu |
| **Source** | [BankInfoSecurity](https://www.bankinfosecurity.com/salesforce-sounds-alarm-over-fresh-data-extortion-campaign-a-30958) |

## Résumé
Le groupe ShinyHunters exploite des comptes guest mal configurés dans les portails Salesforce Experience Cloud, identifiés via Google Dorking. La faille n'est pas technique au sens CVE mais organisationnelle : des accès publics accordés par défaut donnent accès à des données clients sensibles. Pertinent pour les architectes en contexte bancaire/assurance utilisant Salesforce comme CRM avec des APIs exposées. Illustre le risque des configurations permissives dans les couches SaaS — angle NHI indirect (comptes de service guest non gouvernés).

## Actions recommandées
- [ ] Auditer les configurations de comptes guest dans les portails Salesforce Experience Cloud exposés à Internet
- [ ] Appliquer le principe de moindre privilège sur les profils guest et vérifier les permissions d'accès aux objets Salesforce
- [ ] Intégrer les scans de misconfiguration SaaS (SSPM) dans le programme de gestion des risques tiers

---
## 📝 Notes personnelles
