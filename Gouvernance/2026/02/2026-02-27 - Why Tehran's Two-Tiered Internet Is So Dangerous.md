---
title: "Why Tehran's Two-Tiered Internet Is So Dangerous"
date: 2026-02-27
source: "Schneier on Security"
link: "https://www.schneier.com/blog/archives/2026/02/why-tehrans-two-tiered-internet-is-so-dangerous.html"
categorie: "Gouvernance"
action: "keep"
pertinence: 4.0
contrarian: false
vendor_bias: false
uid: "99f017bace9f"
tags:
  - network-security
  - censorship
  - architecture
  - sovereignty
  - digital-rights
  - access-control
  - tiered-access
---

# Why Tehran's Two-Tiered Internet Is So Dangerous

| | |
|---|---|
| **Pertinence** | 4.0/5 |
| **Catégorie** | Gouvernance |
| **Source** | [Schneier on Security](https://www.schneier.com/blog/archives/2026/02/why-tehrans-two-tiered-internet-is-so-dangerous.html) |

## Résumé

Architecture de censure extrême : l'Iran a mis en œuvre un shutdown total (NIN, mobile, SMS, landlines, même Starlink bloqué) plus radical que les précédents, avec démantèlement des couches physiques ET logiques. Le modèle "Internet-e-Tabaqati" institutionnalise un système à deux classes : "white SIM cards" pour loyalistes (accès global sans filtre) vs citoyens ordinaires isolés. L'objectif n'est plus la censure d'URLs mais l'atomisation sociale : empêcher la coordination en temps réel, même via chat de marketplace. Comparé à la Grande Muraille chinoise (écosystème souverain de zéro), ce modèle est plus dangereux car il révoque un droit déjà acquis et crée un apartheid numérique basé sur la loyauté politique.

## Actions recommandées

- [ ] Analyser les parallèles avec les modèles d'accès privilégié dans les systèmes Zero Trust (attestation device, context-aware access) — les white SIMs sont-ils un anti-pattern révélateur ?
- [ ] Documenter le concept de "digital apartheid" comme anti-pattern d'IAM/Access Control pour formations/talks
- [ ] Examiner les implications pour la résilience des systèmes distribués face aux kill switches étatiques
- [ ] Étudier les mécanismes techniques de whitelisting au niveau data center pour comprendre les risques d'architecture centralisée

---
## 📝 Notes personnelles

**Architecture d'exclusion par design** : Le passage de la censorship (blocage sélectif) au shutdown (révocation totale avec whitelist) illustre une évolution vers un contrôle d'accès basé sur l'identité politique. Les "white SIMs" fonctionnent comme des credentials privilégiés dans un système d'access control inversé.

**Analogie Zero Trust inversée** : Là où Zero Trust dit "never trust, always verify", ce modèle dit "never allow, except verified loyalists". La "granular control" devient un outil de répression. L'article note que "simple censorship is insufficient against a tech-savvy population" — conséquence : passer à un modèle d'isolation totale avec exceptions.

**Signal architectural** : La désactivation des features sociales dans les apps non-politiques (chat de ridesharing, marketplace) montre une mentalité "tout canal de communication est une menace". Cela résonne avec les débats actuels sur les backdoors et le chiffrement : quand l'État considère la communication privée comme une menace existentielle, aucune exception n'est acceptable.

**Distinction vs China** : L'analyse comparative est forte. La Chine a construit un écosystème souverain *from scratch* (WeChat, Weibo). L'Iran révoque l'accès à un Internet global déjà utilisé. Plus violent, plus instable, mais aussi plus difficile à maintenir techniquement.

**Pertinence pour les architectes** : Quelles sont les leçons pour la conception de systèmes résilients ? Les kill switches centralisés sont-ils toujours une fonctionnalité désirable, même dans des contextes légitimes (compliance, breach response) ? Comment concevoir des architectures qui résistent à l'abus de privilèges administratifs ?

---
## 📝 Opportunité éditoriale (score: 7/10)

**Thème** : Architecture de censure comme anti-pattern Zero Trust
**Angle** : Les "white SIMs" sont des credentials privilégiés dans un système d'access control dystopique — que nous apprend ce design pattern inversé sur nos propres architectures ?

> 🪝 Hook : "L'Iran vient de déployer Zero Trust à l'envers : never allow, except verified loyalists. Et ça devrait nous inquiéter, pas pour des raisons géopolitiques, mais architecturales."

**Points clés** :
1. Le passage de la censure sélective (URL blocking) au shutdown total avec whitelist illustre une évolution vers l'identity-based access control
2. Les "white SIMs" = privilèges d'accès basés sur la loyauté politique, contournant tous les filtres
3. Analogie avec nos systèmes : context-aware access, device attestation, privileged access management — les mêmes primitives peuvent servir la liberté ou l'oppression
4. Question architecturale : comment concevoir des systèmes qui résistent à l'abus de privilèges admin, même dans des contextes légitimes ?

**Question ouverte** : Si l'identité est vraiment le nouveau périmètre de sécurité, comment empêchons-nous qu'elle devienne le nouveau périmètre de censure ?

**Angle contrarian** : Zero Trust et identity-based access ne sont pas neutres éthiquement — l'architecture porte des valeurs. Les mêmes principes qui sécurisent peuvent aussi isoler.

**Hashtags** : #ZeroTrust #AccessControl #Architecture #DigitalRights #IAM #Security #NetworkArchitecture
