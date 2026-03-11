---
title: "How Healthcare Can Get Started Addressing Post-Quantum Risk"
date: 2026-03-11
source: "BankInfoSecurity"
link: "https://www.bankinfosecurity.com/interviews/how-healthcare-get-started-addressing-post-quantum-risk-i-5530"
categorie: "actu"
action: borderline
pertinence: 2.5
contrarian: false
vendor_bias: false
uid: "https://www.bankinfosecurity.com/interviews/how-healthcare-get-started-addressing-post-quantum-risk-i-5530"
tags:
  - post-quantum
  - cryptography
  - healthcare
  - risk-management
  - crypto-agility
---

# How Healthcare Can Get Started Addressing Post-Quantum Risk

| | |
|---|---|
| **Pertinence** | 2.5/5 |
| **Catégorie** | Actu |
| **Source** | [BankInfoSecurity](https://www.bankinfosecurity.com/interviews/how-healthcare-get-started-addressing-post-quantum-risk-i-5530) |

## Résumé
Ali Youssef (Henry Ford Health) alerte sur la procrastination généralisée dans le secteur santé face au risque post-quantique. L'argument principal : les données médicales ont une durée de vie de confidentialité très longue, ce qui les rend vulnérables aux attaques "harvest now, decrypt later". La crypto-agilité est présentée comme prérequis avant même la migration PQC. Pertinent de façon indirecte pour les architectures API : les tokens OAuth/JWT signés avec RSA/EC sont dans le scope de la menace quantique à horizon 5-10 ans.

## Actions recommandées
- [ ] Initier un inventaire cryptographique des APIs exposées (algorithmes de signature des tokens, TLS versions)
- [ ] Évaluer la crypto-agilité des Authorization Servers en production (support CRYSTALS-Dilithium, etc.)
- [ ] Suivre les travaux NIST PQC et leur intégration dans les stacks OAuth/OIDC (draft OpenID PQC)

---
## 📝 Notes personnelles
