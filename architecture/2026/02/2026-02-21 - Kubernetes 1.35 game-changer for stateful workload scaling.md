---
title: "Why Kubernetes 1.35 is a game-changer for stateful workload scaling"
date: 2026-02-21
source: "The New Stack"
link: "https://thenewstack.io/kubernetes-vpa-inplace-resize/"
categorie: "Architecture"
action: borderline
pertinence: 2.0
contrarian: false
vendor_bias: false
uid: "https://thenewstack.io/kubernetes-vpa-inplace-resize/"
tags:
  - kubernetes
  - vpa
  - autoscaling
  - stateful
  - infrastructure
---

# Why Kubernetes 1.35 is a game-changer for stateful workload scaling

| | |
|---|---|
| **Pertinence** | 2/5 |
| **Catégorie** | Architecture |
| **Source** | [The New Stack](https://thenewstack.io/kubernetes-vpa-inplace-resize/) |

## Résumé
Kubernetes 1.35 passe l'In-Place Pod Resize en GA et introduit le mode VPA InPlaceOrRecreate. L'impact direct sur la sécurité API est limité, mais le scaling dynamique sans redémarrage des pods a des implications pour les Authorization Servers (Keycloak, etc.) et les sidecars Zero Trust (Envoy, SPIFFE/SPIRE) qui opèrent dans des environnements Kubernetes en production bancaire. Pertinence périphérique.

## Actions recommandées
- [ ] Évaluer l'impact du VPA in-place resize sur les déploiements d'Authorization Servers et sidecars SPIFFE/SPIRE en production

---
## 📝 Notes personnelles
