---
title: "One-Time Passcodes Are Gateway for Financial Fraud Attacks"
date: 2026-04-06
source: "BankInfoSecurity"
link: "https://www.bankinfosecurity.com/one-time-passcodes-are-gateway-for-financial-fraud-attacks-a-31341"
categorie: "Sécurité"
action: keep
pertinence: 3.5
contrarian: true
vendor_bias: false
uid: "https://www.bankinfosecurity.com/one-time-passcodes-are-gateway-for-financial-fraud-attacks-a-31341"
tags:
  - OTP
  - SCA
  - fraude
  - authentification
  - DSP2
  - IAM
---

# One-Time Passcodes Are Gateway for Financial Fraud Attacks

| | |
|---|---|
| **Pertinence** | 3.5/5 |
| **Catégorie** | Sécurité |
| **Source** | [BankInfoSecurity](https://www.bankinfosecurity.com/one-time-passcodes-are-gateway-for-financial-fraud-attacks-a-31341) |

## Résumé
🔄 CONTRARIAN — L'article remet en question la fiabilité des OTP SMS comme contrôle d'authentification primaire pour les institutions financières. Alors que DSP2/SCA a imposé l'OTP comme socle de l'authentification forte, les fraudeurs exploitent systématiquement les faiblesses du canal SMS (SIM swapping, SS7 interception, phishing OTP en temps réel) pour conduire des attaques ATO et des fraudes paiement. Le rapport pointe une tendance croissante et structurelle, pas un incident isolé. Cela challenge directement l'hypothèse selon laquelle « SCA = OTP SMS » suffit dans le contexte réglementaire européen. La vraie question est : DSP3/PSR va-t-il forcer une migration vers des méthodes FIDO2/passkeys ou rester sur un OTP fragilisé ?

## Actions recommandées
- [ ] Analyser l'exposition OTP SMS dans les architectures SCA bancaires actuelles et cartographier les vecteurs d'attaque
- [ ] Évaluer la migration vers FIDO2/WebAuthn ou CIBA pour les flows d'authentification sensibles
- [ ] Intégrer ce retex dans la réflexion DSP3/PSR : l'OTP SMS peut-il encore satisfaire les exigences SCA ?
- [ ] Angle LinkedIn : "L'OTP est mort, DSP3 doit le reconnaître"

---
## Notes personnelles
Contrarian fort sur l'axiome #2 (FAPI/SCA) et #4 (identité comme périmètre). Si le canal d'authentification est compromis, le meilleur protocole d'autorisation ne sert à rien. Connexion directe avec le chapitre SCA/CIBA du livre.
