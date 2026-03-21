---
title: "Zero Trust for Non-Technical Leaders: What You Need to Know"
date: 2025-03-20
source: "Spruce ID"
link: "https://blog.spruceid.com/zerotrust-zero-trust-for-non-technical-leaders-what-you-need-to-know/"
categorie: "zero-trust"
action: "keep"
pertinence: 3.5
contrarian: false
vendor_bias: true
uid: "e263d09b7990"
tags:
  - zero-trust
  - government
  - vulgarisation
  - architecture
  - spruce-id
---

# Zero Trust for Non-Technical Leaders: What You Need to Know

| | |
|---|---|
| **Pertinence** | 3.5/5 |
| **Catégorie** | Zero Trust |
| **Source** | [Spruce ID Blog](https://blog.spruceid.com/zerotrust-zero-trust-for-non-technical-leaders-what-you-need-to-know/) |

## Résumé

⚠️ **Contenu vendor** — Spruce ID propose une vulgarisation pédagogique du Zero Trust pour leaders gouvernementaux non techniques. Article bien structuré qui traduit les principes ZT (never trust, always verify) en bénéfices métier : réduction fraude, containment des breaches, conformité NIST 800-53/HIPAA. **Intéressant pour l'approche communicationnelle**, mais reste superficiel sur l'implémentation réelle et pousse vers le portfolio Spruce (verifiable credentials). Le modèle "identity + device + context" est classique ; manque la discussion sur les compromis architecturaux et la complexité opérationnelle.

## Actions recommandées

- [ ] Réutiliser la métaphore "Portuguese phrase book" pour expliquer les limites de l'authN sans authZ continue
- [ ] Intégrer les 3 questions ("What assets fall outside our model?", "How do we verify identity + device?", "Can we implement incrementally?") dans un framework de diagnostic client
- [ ] Challenger l'approche "phased" : quels sont les anti-patterns d'implémentation incrémentale qui échouent ?

---

## 📝 Notes personnelles

**Forces** :
- Bon angle pédagogique : "trust but verify" → "never trust, always verify"
- Référence SolarWinds pertinente pour illustrer le risque de lateral movement
- Questions structurées utiles pour les décideurs

**Faiblesses** :
- Pas de discussion sur les trade-offs : coût, friction utilisateur, complexité opérationnelle
- Vision binaire (ZT = bien, perimeter = obsolète) sans nuance
- Manque de retex concrets : combien coûte réellement une implémentation ZT pour une agence gouvernementale ?
- Vendor bias évident : pousse vers verifiable credentials sans comparer aux alternatives

**Lien avec NHI** : L'article se concentre sur human identity (caseworker, contractor) mais n'aborde PAS les service accounts, API keys, machine-to-machine flows qui représentent 70%+ des identités en environnement gouvernemental moderne. C'est un angle mort typique des approches ZT centrées sur IAM humain.

**Potentiel éditorial** : Moyen. Pourrait être retourné en angle contrarian : "Zero Trust for Humans Isn't Enough: Why NHI Is the Blind Spot in Government Security."

